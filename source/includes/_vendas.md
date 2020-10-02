# Vendas

## URL's

Produção: http://api.focuslojas.com.br/sales

Método HTTP | Caminho | Descrição
--|--|--
GET | /sales | Consulta todas as variações cadastradas.
POST | /sales | Cria uma nova venda.

## Campos

Campos | Descrição
--|--
id | Identificador do registro.
number | Número da venda registrado no PDV.
status | Situação da venda, permite os valores: 'realized' (realizado), 'canceled' (cancelado pelo retaguarda | usado apenas em sistemas não fiscais), 'canceled_pos', (cancelado pelo PDV), 'unfinished' (não finalizado, ou seja, cancelado pelo PDV antes da impressão do valor total).
pos_id | Identificador do PDV.
pos_user_id | Identificador do usuário do PDV (vendedor).
sold_at | Data e hora da venda no formato ISO8601.
ccf | Contador de cupom fiscal.
coo | Número do cupom fiscal (Contador de Ordem da Operação).
consumer_nf_serie | Série da nota fiscal manual emitida.
consumer_nf_number | Número da nf manual emitida.
total_cost_returned | Valor de custo total devolvido.
total_cost_sold | Valor de custo total vendido.
total_price_returned | Valor de venda total devolvido.
total_price_sold | Valor de venda total vendido.
discount | Desconto da venda.
credit | Crédito ao cliente, caso ele tenha pago a maior.
percent_discount | Desconto em percentual (0 a 100).
total_reimbursement | Valor total do reembolso ao cliente.
net_value | Valor líquido da venda (total pago - valor reembolsado - saldo utilizado).
total_installments | Somatório do número de parcelas de pagamento recebidas. (Exemplo: pagamento em dinheiro e 2x no cartão resulta em 3 parcelas).
discount_auth_user_id | Id do usuário que liberou desconto na venda.
numero_nfce | Número da NFCe.
serie_nfce | Série da NFCe.
chave_nfce | Chave da NFCe.
protocolo_nfce | Protocolo da NFCe.
url_xml_nfce | URL do XML da NFCe.
nfce_contingencia | indica se a nfce foi emitida em contingência offline.
nfce_contingencia_efetivada | indica se a emissão em contingência já foi efetivada na receita.
url_xml_cfe | URL do xml da CFe emitida por SAT fiscal.
customer | Lista de dados do cliente.
pos | Lista de dados do PDV.
pos_entries | Lista de dados de entradas do PDV (pagamentos). 
sold_items | Lista de dados dos itens vendidos.
returned_items | Lista de dados dos itens devolvidos em uma venda.

## Campos da lista customer

Este grupo de campos armazena os dados do cliente, retornando as seguintes informações nas consultas:

```json
```

Campo | Descrição
--|--
id | Identificador do cliente.
original_id | Identificador original do cliente.

## Campos da lista pos

Este grupo de campos armazena os dados do PDV, retornando as seguintes informações nas consultas:

```json
```

Campo | Descrição
--|--
number | Número do PDV.
ecf_serial_number | Número de série.

## Campos da lista pos_entries

Este grupo de campos armazena os dados de entradas do PDV (pagamentos), retornando as seguintes informações nas consultas:

```json
```

Campo | Descrição
--|--
entry_type | Tipo do pagamento (Dinheiro, Cartão, TEF, Cheque, Carnê ou Saldo Utilizado).
card_type | Quando cartão, informa **D** - Débito ou **C** - Crédito.
num_installments | Número de parcelas do pagamento.
value | Valor total do pagamento.
description | Descrição.
tef_identificacao | Identificação TEF.
tef_nsu | NSU do TEF.
tef_rede | Rede do TEF.
tef_finalizacao | Finalização TEF.
auth_number | Número de autorização do TEF.
card_info_snapshot | Quando o entry_type = "Cartão", este nó irá conter as informações do cartão utilizado.
bonus_id | id interno no focus lojas do bonus usado, caso o tipo seja Bônus.
bonus_original_id | Lista de valores referentes ao Bônus.
check | Lista de valores referentes a forma de pagamento Cheque.

### Campos da lista bonus_original_id

Este campo recebe o id externo, quando presente, do bônus usado caso o tipo seja Bônus.

Existem duas listas aqui, são elas:

* **card_brand**: Contém informações do cartão.
	1. name: Nome (fixo).
	2. tef_parameter: Parâmetro TEF
* **card_company**: Contém informações da credenciadora do cartão. 
	1. name: Nome (fixo).
	2. tef_parameter: Parâmetro TEF.

### Campos da lista check

Quando o entry_type = "Cheque", este nó irá conter as informações do cheque utilizado.

Campo | Descrição
--|--
id | Identificador do sistema.
name | Nome do emitente do cheque.
cnpj_cpf | CNPJ ou cpf do emitente.
bank_num | Código do banco.
branch_num | Número da agência.
account_num | Número da conta.
check_num | Número do cheque.
date | Data do cheque.
value | Valor do cheque.
comment | Observação.
cmc7 | CMC7 do cheque.

## Campos da lista sold_items

Lista contento todos os produtos vendidos, com os seguintes campos:

```json
```

Campo | Descrição
--|--
quantity | Quantidade vendida.
price | Preço unitário de venda.
cost | Preço unitário de custo.
tax_type | Tipo de imposto aplicado (I, N, F, T ou S) representando Isento, Não Tributado, Substituição Tributária, Tributado pelo ICMS, Tributado pelo ISSQN, respectivamente.
tax_rate | Alíquota do imposto.
status | Situação do item, permite os valores: 'realized' (realizado), 'canceled' (cancelado pelo retaguarda - usado apenas em sistemas não-fiscais), 'canceled_pos' (cancelado pelo PDV).

### Campos da lista product

Lista com os dados do produto.

Campo | Descrição
--|--
id | Identificador do produto
original_id | Identificador original
code | Referência


## Campos da lista returned_items

Lista de todos os produtos devolvidos, com os seguintes campos:

```json
```

Campo | Descrição
--|--
product | Lista de dados sobre o produto.
quantity | Quantidade vendida
price | Preço unitário de venda
cost | Preço unitário de custo
tax_type | Tipo de imposto aplicado (I, N, F, T ou S) representando Isento, Não Tributado, Substituição Tributária, Tributado pelo ICMS, Tributado pelo ISSQN, respectivamente
tax_rate | Alíquota do imposto
status | Situação do item, permite os valores: 'realized' (realizado), 'canceled' (cancelado pelo retaguarda - usado apenas em sistemas não fiscais), 'canceled_pos' (cancelado pelo PDV).
original_sale_info | Lista de campos sobre a venda onde este que está sendo devolvido foi vendido. (Campo removido na versão 47).
return_sale | Lista de informações sobre a venda onde este que está sendo devolvido o que foi vendido

### Campos da lista product

Lista com os dados do produto.

Campo | Descrição
--|--
id | Identificador do produto
original_id | Identificador original
code | Referência

### Campos da lista original_sale_info

(Campo removido na versão 47) Informações sobre a venda onde este que está sendo devolvido foi vendido

Campo | Descrição
--|--
sale_id | id da venda em nosso retaguarda
number | número da venda original
store_id | id da loja em nosso retaguarda
store_cnpj | cnpj da loja onde a venda original ocorreu
coo | COO da venda original (se venda foi realizada em ECF)
ccf | CCF da venda original (se venda foi realizada em ECF)
numero_nfce | Número da NFCe da venda original (se venda original foi realizada por NFCe)
numero_cfe_sat | Número do cupom SAT da venda original (se venda original foi realizada em SAT)
cpf | CPF do consumidor da venda original (se existir)
cnpj | CNPJ do consumidor da venda original (se existir)

### Campos da lista return_sale

Informações sobre a venda onde este que está sendo devolvido o que foi vendido:

Campo | Descrição
--|--
id | id da venda em nosso retaguarda
number | número da venda original
coo | COO da venda original (se venda foi realizada em ECF)
ccf | CCF da venda original (se venda foi realizada em ECF)
numero_nfce | Número da NFCe da venda original (se venda original foi realizada por NFCe)
serie_nfce | Série da NFCe da venda original (se venda original foi realizada por NFCe)
numero_cfe_sat | Número do cupom SAT da venda original (se venda original foi realizada em SAT)
store | Lista de dados referentes a identificação da loja.
customer | Lista de dados referentes ao cliente.
pos | Lista de dados referentes ao PDV.

#### Campos da lista store

Lista de dados referentes a identificação da loja.

Campo | Descrição
--|--
id | id da loja em nosso retaguarda
cnpj | cnpj da loja onde a venda original ocorreu


#### Campos da lista customer

Lista de dados referentes ao cliente.

Campo | Descrição
--|--
id | Id do consumidor no nosso retaguarda
cpf | CPF do consumidor da venda original (se existir)
cnpj | CNPJ do consumidor da venda original (se existir)

#### Campos da lista pos

Lista de dados referentes ao PDV.

Campo | Descrição
--|--
id | id do PDV em nosso retaguarda
ecf_serial_number | Número de série do ECF se aplicável
number | Número do PDV


## Criação

Para criar uma nova venda utilize a URL abaixo, alterando para o ambiente desejado (produção ou homologação).

`http://api.focuslojas.com.br/sales`

Utilize o comando HTTP **POST** para enviar o cadastro para nossa API. Envie como corpo da requisição os dados em formato JSON, utilizando os campos listados abaixo.

Ao lado você pode visualizar como é o JSON esperado para criação e como é o JSON devolvido pela API.

> Exemplo de JSON para criação de uma venda.

```json
```

Campo | Descrição
--|--
customer_original_id: Identificador original do cliente
status - Situação da venda, permite os valores: 'realized' (realizado), 'canceled' (cancelado pelo retaguarda - usado apenas em sistemas não-fiscais), 'canceled_pos', (cancelado pelo PDV), 'unfinished' (não finalizado, ou seja, cancelado pelo PDV antes da impressão do valor total)
sold_at: Data e hora da venda no formato ISO8601

### Campos da lista pos_entries_attributes

Lista de todas os pagamentos feitos por esta compra, com os seguintes campos:

Campo | Descrição
--|--
entry_type | Tipo do pagamento (Dinheiro, Cartão, TEF, Cheque, Carnê ou Saldo Utilizado).
card_type | Quando cartão, informa "D" - Débito ou "C" - Crédito.
num_installments | Número de parcelas do pagamento. Usado em carnê ou pagamentos em crédito.
value | Valor total do pagamento.
card_brand | Nome do cartão. Permite os valores: Visa, American Express, Mastercard, Senff, Hipercard, Diners, Regicred, Banrisul, Elo, Diners, Sicredi, VerdeCard, BanesCard.
card_company | Nome da credenciadora de cartão. Permite os valores: American Express, Rede, Cielo, Senff, GetNet, Regicred, Vero, PagSeguro, Paypal, Mercadopago.

### Campos da lista sold_items_attributes

Lista de todos os produtos vendidos, com os seguintes campos:

Campo | Descrição
--|--
product_id | Identificador do produto.
quantity | Quantidade vendida.
price | Preço unitário de venda.


### Campos da lista returned_items_attributes

Lista de todos os produtos devolvidos, com os seguintes campos:

Campo | Descrição
--|--
product_id | Identificador do produto.
id | Identificador do produto.
quantity | Quantidade vendida.
price | Preço unitário de venda.
status | Situação do item, permite os valores: 'realized' (realizado), 'canceled' (cancelado pelo retaguarda - usado apenas em sistemas não-fiscais), 'canceled_pos' (cancelado pelo PDV).

## Consulta

Para consultar todos os cadastros de variações utilize a URL abaixo, alterando para o ambiente desejado (produção ou homologação).

`http://api.focuslojas.com.br/sales`

Utilize o comando HTTP **GET** nesta consulta. Os campos retornados serão os mesmos campos que foram listados no menu [Campos](#campos).

Ao lado você pode visualizar como é o JSON de resposta da nossa API.

> JSON enviado pela API Focus Lojas como resposta da consulta.

```json
```

## Erros