# kits

Este recurso representa o cadastro de um kit de produtos.

## URL's

Produção: http://api.focuslojas.com.br/kits

Método HTTP | Caminho | Descrição
--|--|--
GET | /kits | Consulta de departamentos.
POST | /kits | Criação de uma novo departamento.

## Campos

Tipo de valor | Campo | Descrição
--|--|--
int | id | Identificador do sistema.
int | original_id | Identificador externo.
string | code | Referência do kit (será criada automaticamente se não informada).
string | barcode | Código de barras do kit (será criado automaticamente se não informadao).
string | name* | Nome do kit.
bool | active* | Indica se o kit esta ativo ou não.
array| items_attributes* | Lista de items que compõe o produto. Cada item do array pode conter os campos abaixo.

### Campos da lista items_attributes

Tipo de valor | Campo | Descrição
--|--|--
int | product_id** - Referência do produto - Pode ser substituído pelo campo original_product_id
int | supplier_id** - Referência do fornecedor
str | code** - referência do produto
int | quantity* - Quantidade do produto
decimal| price* - Preço do produto

(\*) Campos obrigatórios.

Para identificação do produto que compõe o kit pode ser informado o **product_id**, o **original_product_id** ou o par code e **supplier_id**.

## Criação

Para criar um novo departamento utilize a URL abaixo, alterando para o ambiente desejado (produção ou homologação).

`http://api.focuslojas.com.br/kits`

Utilize o comando HTTP **POST** para enviar o cadastro para nossa API. Envie como corpo da requisição os dados em formato JSON, utilizando os campos listados abaixo.

Ao lado você pode visualizar como é o JSON esperado para criação e como é o JSON devolvido pela API.

Sempre que um kit for atualizado deverá ser passado novamente todos os itens que compõe o kit. O sistema irá verificar se houve diferença entre os itens e irá desativar automaticamente os itens que não existem mais.

> Exemplo de JSON para criação de um kit.

```json
```

## Consulta

Para consultar os cadastros de departamentos utilize a URL abaixo, alterando para o ambiente desejado (produção ou homologação).

`http://api.focuslojas.com.br/kits`

Utilize o comando HTTP **GET** nesta consulta. Os campos retornados serão os mesmos campos que foram listados no menu [Campos](#campos).

Ao lado você pode visualizar como é o JSON de resposta da nossa API.

> JSON enviado pela API Focus Lojas como resposta da consulta.

```json
```

## Erros	