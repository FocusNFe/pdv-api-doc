# Variações

Este recurso representa uma dimensão dos itens de grade de um produto (ex: cor, tamanho, etc). Cada produto pode utilizar no máximo 3 dimensões. Normalmente cada dimensão especifica um produto de mesmo preço, mas isto pode ser configurável. Seu uso é opcional, mas muito comum em segmentos como vestuário.

* Possui campo version: sim
* Possui campo original_id: não

## URL's

Produção: http://celero.focuslojas.com.br/dimensions

Método HTTP | Caminho | Descrição
--|--|--
GET | /dimensions | Consulta todas as variações cadastradas.

## Campos

```json
//Exemplo de dado de entrada
{
   "dimension":{
      "name":"Cor",
      "values_attributes":[
         {
            "value":"Branco"
         },
         {
            "value":"Azul"
         }
      ]
   }
}
```

```json
//Exemplo de resultado de consulta
{
  "dimension_values": [
    {
      "id": 2,
      "value": "Azul",
      "version": 15,
      "dimension_id": 1,
      "domain_id": 1
    },
    {
      "id": 1,
      "value": "Branco",
      "version": 14,
      "dimension_id": 1,
      "domain_id": 1
    }
  ],
  "dimension": {
    "id": 1,
    "name": "Cor",
    "version": 13,
    "domain_id": 1,
    "value_ids": [
      2,
      1
    ]
  }
}
```


Tipo de valor | Campos | Descrição
--|--|--
integer | id | Identificador do registro (apenas leitura)
string | name | Nome da dimensão
Array | values| Array de valores da variação

Cada valor da variação pode conter:

Tipo de valor | Campos | Descrição
--|--|--
id | id | Identificador do registro (apenas leitura)
string | value | valor da dimensão

## Consulta

Para consultar todos os cadastros de variações utilize a URL abaixo, alterando para o ambiente desejado (produção ou homologação).

`http://celero.focuslojas.com.br/dimensions`

Utilize o comando HTTP **GET** nesta consulta. Os campos retornados serão os mesmos campos que foram listados no menu [Campos](#campos).

Ao lado você pode visualizar como é o JSON de resposta da nossa API.

> JSON enviado pela API Focus Lojas como resposta da consulta.

```json
```

## Erros
