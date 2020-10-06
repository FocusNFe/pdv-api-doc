# Estoque

Este modelo representa o estoque de um determinado produto em uma determinada loja. É administrado pela API mas pode ser consultado por sistemas terceiros.
A quantidade em estoque é sempre referente a um item de variação, quando aplicável, nunca do produto principal.

* Possui campo version: sim
* Possui campo original_id: não

## URL's

Produção: http://api.focuslojas.com.br/inventories.json

Método HTTP | Caminho | Descrição
--|--|--
GET | /inventories.json | Consulta
GET | /inventories/ID.json | Consulta de registro específico
POST | /inventories.json | Criação de um novo registro
PUT | /inventories/ID.json | Alteração de um registro

## Campos

Tipo de valor | Campo | Descrição
--|--|--
int | product_id | id do produto
decimal | in_stock_quantity | quantidade em estoque da loja
decimal | sold_quantity | quantidade vendida do produto
