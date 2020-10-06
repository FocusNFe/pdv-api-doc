# Tipos de produto

Este recurso representa o tipo de um produto. Normalmente é uma classificação interna da constituição do produto (ex: calça, blusa, etc.). Normalmente é de mais interesse do lojista (como organização interna) do que do consumidor final.
Seu uso é opcional.

* Possui campo version: sim
* Possui campo original_id: não

## URL's

Produção: http://celero.focuslojas.com.br/product_types.json

Método HTTP | Caminho | Descrição
--|--|--
GET | /product_types.json | Consulta de tipos de produto.
GET | /product_types/ID.json | Consulta de um tipo.
POST | /product_types.json | Criação de uma novo tipo.
PUT | /product_types/ID.json | Alteração de tipo.

## Campos

Tipo de valor | Campos | Descrição
--|--|--
integer | id | Identificador do registro (apenas leitura)
string | name | Nome do tipo do produtos
