# Vale Presente

Representa um vale presente. Um vale presente pode ser criado externamente ou pelo próprio PDV quando há devolução de alguma venda.

* Possui campo version: não
* Possui campo original_id: sim, mas de uso exclusivo do PDV

## URL's

Produção: http://celero.focuslojas.com.br/gift_coupons.json

Método HTTP | Caminho | Descrição
--|--|--
GET | /gift_coupons.json | Consulta
GET | /gift_coupons/ID.json | Consulta de registro específico
POST | /gift_coupons.json | Criação de um novo registro
PUT | /gift_coupons/ID.json | Alteração de um registro

## Campos

Abaixo todos os campos usados para vale presente:


Tipo do valor | Campos | Descrição
--|--|--
int | id | Identificador do sistema.
string | description | Descrição opcional deste vale presente.
string | code | O código do bônus composto por 12 caracteres (Não é necessário informar o código na criação do bônus pois o Focus Lojas se encarrega desta criação).
date | valid_until* | Data de validade deste vale presente.
decimal | value* | Valor deste vale presente.
int | customer_id* | Id do cliente no Focus Lojas.
string | status* | Qual o status deste vale presente (valid, void, used).
date | used_at | Se o vale presente já foi usado indica a data em que o uso ocorreu.
int | sale_id | Id da Venda em que foi utilizdo.
