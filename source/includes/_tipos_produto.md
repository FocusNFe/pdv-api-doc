# Tipos de produto

Este recurso representa o tipo de um produto. A API fornece método apenas para consulta, devendo ser cadastrado dentro do próprio sistema de retaguarda.

## URL's

Produção: http://api.focuslojas.com.br/product_types

Método HTTP | Caminho | Descrição
--|--|--
GET | /product_types | Consulta 

## Campos

Tipo de valor | Campos | Descrição
--|--|--
integer | id | Identificador do registro
string | name | Nome do tipo do produtos


## Consulta

Para consultar os cadastros dos tipos de produtos utilize a URL abaixo, alterando para o ambiente desejado (produção ou homologação).

`http://api.focuslojas.com.br/product_types`

Utilize o comando HTTP **GET** nesta consulta. Os campos retornados serão os mesmos campos que foram listados no menu [Campos](#campos).

Ao lado você pode visualizar como é o JSON de resposta da nossa API.

> JSON enviado pela API Focus Lojas como resposta da consulta.

```json
```

## Erros