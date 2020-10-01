# Variações

Este recurso representa uma dimensão dos itens de grade de um produto. Cada produto pode utilizar no máximo 3 dimensões. A API fornece método apenas para consulta, devendo ser cadastrado dentro do próprio sistema de retaguarda.

## URL's

Produção: http://api.focuslojas.com.br/dimensions

Método HTTP | Caminho | Descrição
--|--|--
GET | /dimensions | Consulta todas as variações cadastradas.

## Campos

Tipo de valor | Campos | Descrição
--|--|--
integer | id | Identificador do registro
string | name | Nome da dimensão
Array | values | Lista de valores que a dimensão aceita:
id | id | Identificador do registro
string | value | valor da dimensão

## Consulta

Para consultar todos os cadastros de variações utilize a URL abaixo, alterando para o ambiente desejado (produção ou homologação).

`http://api.focuslojas.com.br/dimensions`

Utilize o comando HTTP **GET** nesta consulta. Os campos retornados serão os mesmos campos que foram listados no menu [Campos](#campos).

Ao lado você pode visualizar como é o JSON de resposta da nossa API.

> JSON enviado pela API Focus Lojas na consulta de todos os registros.

```json
```

## Erros