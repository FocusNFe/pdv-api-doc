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

Produção: http://api.focuslojas.com.br/

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

### Campos de objetos aninhados

## Formato do JSON de resposta

### Objetos relacionados

## Facilidades de sincronização

### Enviando dados: Sincronização com ID original

### Recebendo dados: Entendendo o campo de versão
