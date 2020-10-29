# Introdução

O Focus Lojas disponibiliza uma API utilizando a arquitetura REST (Representational State Transfer) onde é utilizada uma URL em conjunto com os verbos disponíveis pelo protocolo HTTP: POST, GET, PUT e DELETE para simular as operações CRUD (*C*reate, *R*etrieve, *U*pdate e *D*elete) de um dado recurso. Um recurso geralmente representa um objeto no banco de dados.

Por exemplo, suponha um recurso chamado “Loja” que representa um estabelecimento identificado por um número sequencial (id). Podemos ter as seguintes operações:

Operação | Chamada HTTP
---|---
Recupera lista de lojas cadastradas | GET /lojas
Cria uma nova loja | POST /lojas (nos dados do POST serão enviados os campos da loja)
Recupera dados de uma loja cujo id é 2 | GET /lojas/2
Altera dados de uma loja cujo id é 2 | PUT /lojas/2
Deleta uma loja cujo id é2 | DELETE /lojas/2

## URL

Produção: https://pdv-api.celero.mobi/

## Respostas

As chamadas HTTP devolvem as informações em formato JSON.

A reposta do status HTTP também é significativa. Se o status de resposta for 200 (Ok) significa que a solicitação foi executada com sucesso. Quando um novo recurso é criado, o status devolvido é o 201 (Created). Uma solicitação com erro (por exemplo, tentar criar um estabelecimento sem o CNPJ ou CPF) resulta no status 422 (Unprocessable Entity).

## Autenticação

Os mecanismos de autenticação são baseados em um access token secreto que é criado para cada loja que irá acessar o sistema e associado ao seu número de série. Pode ser criado um token de acesso e um número de série que não esteja associado a uma loja física, para representar uma unidade administrativa, por exemplo. Desta forma, todas as requisições feitas a API deverão conter os parâmetros **access_token** e **serial_number** preenchidos.

Ainda é necessário que se passe a versão da API implementada através do parâmetro **api_version**.

A integridade e sigilo são garantidas a partir do protocolo HTTPS.

Parâmetros | Valor
--|--
access_token | Token secreto da loja.
serial_number | Número de série da loja.
api_version | Versão da API. Atualmente, aceita apenas '1'.


> Exemplo de consulta:

```shell

curl -H 'Authorization: Token token=TOKEN_AQUI, serial_number=NUMERO_DE_SERIE, api_version=1' https://app.focuslojas.com.br/customers.json

```

## Formato do JSON de entrada

```json
// Exemplo objeto simples
{
  "model": {
    "campo_1":"valor_1",
    "campo_2":"valor_2",
    "campo_n":"valor_3"
  }
}
```

O JSON de entrada de um modelo chamado "model" com campos "campo_1", "campo_2", ..., "campo_n" deverá ser enviado como um objeto com a chave "model" conforme exemplo.


### Campos de objetos aninhados

```json
// Exemplo com objeto aninhado: master-detail
{
  "model": {
    "campo_1":"valor_1",
    "campo_2":"valor_2",
    "campo_n":"valor_n",
    "model_items_attributes": [
      {
      	"campo_item_1":"valor_item_1",
      	"campo_item_n":"valor_item_n",
      }
    ]
  }
}
```
Objetos aninhados quando enviados junto com o objeto relacionado, deverão ter o sufixo "_attributes". Eventualmente alguns endpoints podem disponibilizar metadados nesta estrutura.


## Formato do JSON de resposta

De forma análoga, a resposta também irá conter uma chave indexando um objeto. Esta chave pode estar no plural caso o endpoint seja para listar mais de um objeto ou no singular caso seja a busca de um objeto apenas.

### Objetos relacionados

```json
// Exemplo com objeto aninhado: master-detail
{
  "model_items": [
    {
      "id": 123,
      "campo_item_1":"valor_item_1",
      "campo_item_n":"valor_item_n"
    },
    {
      "id": 124,
      "campo_item_1":"valor_item_A",
      "campo_item_n":"valor_item_Z"
    }
  ],
  "model": {
    "campo_1":"valor_1",
    "campo_2":"valor_2",
    "campo_n":"valor_n",
    "model_item_ids": [ 123, 124 ]
  }
}
```

Ao buscar objetos que contém outros objetos aninhados (relação de um para muitos) o objeto principal irá conter uma lista de ids apontando para o objeto correspondente.

### Paginação

Ao buscar uma coleção de objetos , a API por default devolve 30 registros por vez. É incluída a chave "meta" que inclui uma variável chamada "total" com o número de registros da consulta.

A próxima página da consulta pode ser acessada indicando o parâmetro offset na URL, por exemplo:

* Página 1: https://pdv-api.celero.mobi/customers.json
* Página 2: https://pdv-api.celero.mobi/customers.json?offset=30
* Página 3: https://pdv-api.celero.mobi/customers.json?offset=60

## Facilidades de sincronização

A sincronização entre sistemas oferece alguns desafios, por isso usamos duas funcionalidades que ajudam a tornar a sincronização mais fácil do que apenas usar as operações convencionais de um CRUD.

### Enviando dados: Sincronização com ID original

Quando temos o mesmo dado em dois sistemas distintos, normalmente é necessário algum tipo de mapeamento de identificadores dos registros em cada sistema para poder fazer a sincronização com sucesso. Nos modelos mais importantes este mapeamento é feito do lado da API.

Alguns modelos contém um campo chamado "original_id", cuja significado é o "id que originou este registro". Por exemplo, normalmente o sistema terceiro já contém uma base de produtos ou uma base de clientes, desta forma, o id original será o identificador usado no sistema terceiro. Ao criar um registro com este campo, a API primeiramente verifica se este registro com o original_id especificado já existe, caso positivo, atualiza o registro, caso contrário ele é criado.

O campo original_id pode ser utilizado também em chaves estrangeiras. Por exemplo, um "KitItem" faz referência a um "Product", podemos referencia-lo tanto usando product_id quanto original_product_id . Neste último caso será buscado o produto pelo seu id original.

Com este mecanismo temos uma operação de criação idempotente, ou seja, independente de quantas vezes a requisição for enviada, ela terá o mesmo resultado. Isto pode simplificar bastante a sincronização do lado do sistema terceiro.

### Recebendo dados: Entendendo o campo de versão

Quando é feita sincronização entre dois sistemas, nem sempre é interessante fazer busca paginada de objetos, pois normalmente temos interesse apenas nos registros novos (que o sistema terceiro não conhece). Isto é útil para os modelos que são gerados como resultado das operações do Focus Lojas, como por exemplo a movimentação de caixa ou as próprias vendas recebidas.

Para este tipo de sincronização, nós incluímos um campo chamado "version" (versão). Cada registro salvo incrementa uma versão global ao conjunto de lojas. Desta forma, o sistema terceiro precisa apenas armazenar a última versão de seu conhecimento para cada conjunto de lojas (de uma mesma propriedade). Por exemplo:

Para buscar todas as vendas deve-se chamar o endpoint https://pdv-api.celero.mobi/sales.json?version=0. Ao fim do processamento desta lista, o sistema terceiro deverá armazenar o último version que foi importado. Caso seja o version=123 a próxima consulta deverá ser https://pdv-api.celero.mobi/sales.json?version=123 que irá buscar apenas as versões maiores que 123, e assim por diante.

## Formato desta documentação

O restante desta documentação está organizada como uma referência de modelos disponíveis via API. São listadas as operações possíveis, seus campos e quaisquer observações ou cuidados especiais.
