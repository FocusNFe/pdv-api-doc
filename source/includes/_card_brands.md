# Bandeiras de cartões

Esta seção descreve como buscar as bandeiras de cartões (ex: Visa, Mastercard, etc.) disponíveis no sistema. É uma informação somente de leitura, configurada no aplicativo.

* Possui campo version: não
* Possui campo original_id: não

Esta informação é global ao sistema, não se aplica filtro por domínio ou loja.


## URL's

Produção:  https://pdv-api.celero.mobi/card_brands.json

Método HTTP | Caminho | Descrição
--|--|--
GET | /card_brands.json | Consulta todas as bandeiras

## Campos

Campos | Descrição
--|--
id | Identificador do registro.
name | Nome do cartão
tef_parameter | Parâmetro TEF a ser usado na integração com máquinas TEF (crédito)
debit_tef_parameter | Parâmetro TEF a ser usado na integração com máquinas TEF (débito)
