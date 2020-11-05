# Credenciadoras

Esta seção descreve como buscar as credenciadoras de cartões (ex: Rede, Cielo, etc.) disponíveis no sistema. É uma informação somente de leitura, configurada no aplicativo.

* Possui campo version: não
* Possui campo original_id: não

Esta informação é global ao sistema, não se aplica filtro por domínio ou loja.


## URL's

Produção:  https://pdv-api.celero.mobi/card_companies.json

Método HTTP | Caminho | Descrição
--|--|--
GET | /card_companies.json | Consulta todas as credenciadoras

## Campos

Campo | Descrição
--|--
id | Identificador do registro
name | Nome da credenciadora
tef_parameter | Parâmetro TEF a ser usado na integração com máquinas TEF
cnpj | CNPJ da empresa
inscricao_estadual | IE da empresa
suframa | Suframa da empresa se aplicável
end | Logradouro da empresa
compl | Complemento do endereço
bairro | Bairro
cod_mun | Código IBGE do município da empresa
cod_pais | Código IBGE do país da empresa
card_company_brand_ids | Lista de IDs de bandeiras aceitos por esta credenciadora
