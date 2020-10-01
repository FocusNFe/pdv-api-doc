# Vale Presente

## URL's

Produção: http://api.focuslojas.com.br/gift_coupons

Método HTTP | Caminho | Descrição
--|--|--
POST | gift_coupons | Cria um novo vale presente.

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

## Criação

Para criar um novo cadastro de vale presente utilize a URL abaixo, alterando para o ambiente desejado (produção ou homologação).

`http://api.focuslojas.com.br/gift_coupons`

Utilize o comando HTTP **POST** para enviar o cadastro para nossa API. Envie como corpo da requisição os dados em formato JSON, utilizando os campos listados na seção [Campos](#campos)

Ao lado você pode visualizar como é o JSON esperado para criação e como é o JSON devolvido pela API.

> Exemplo de JSON para criação de um cliente.

```json

JSON DE EXEMPLO AQUI

```

## Erros