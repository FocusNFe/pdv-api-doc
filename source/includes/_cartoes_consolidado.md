# Cartões (Consolidado)

Esta seção descreve como buscar as informações de cartão por loja. Estes dados são os que o PDV se preocupa em buscar. Os dados estão modelados de uma forma mais simplificada para a modelagem do PDV.

* Possui campo version: sim
* Possui campo original_id: não

Este endpoint foge um pouco do padrão definido nos demais endereços pois todas as informações são enviadas de uma vez, sem paginação (pois potencialmente são poucos registros).


## URL's

Produção: https://pdv-api.celero.mobi/card_infos.json

Método HTTP | Caminho | Descrição
--|--|--
GET | /card_infos.json | Consulta todas as informações sobre cartões desta loja

## Campos

Este endpoint irá devolver um arquivo json com 3 chaves: card_infos, card_brands e card_companies. Abaixo são descritos os campos de forma separada por grupo.


### card_brands

Este grupo descreve as bandeiras utilizadas na loja.

Campos | Descrição
--|--
id | Identificador do registro.
name | Nome do cartão
tef_parameter | Parâmetro TEF a ser usado na integração com máquinas TEF (crédito)
debit_tef_parameter | Parâmetro TEF a ser usado na integração com máquinas TEF (débito)

## card_companies

Este grupo descreve as credenciadoras utilizadas na loja.

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

## card_infos

Este grupo descreve a configuração do par [credenciador, bandeira] da loja.

id | Identificador do registro
active | Se esta configuração está ativa ou não
accepts_debit | Aceita débito?
accepts_installment_credit | Aceita crédito parcelado?
accepts_installment_debit | Aceita débito parcelado?
accepts_revolving_credit | Aceita crédito à vista?
card_brand_id | ID da bandeira
card_company_config_id | ID da credenciadora
max_num_installments | Número máximo de parcelas (crédito)
version | Versão da configuração
debit_interest | Taxa do débito (uso futuro)
revolving_credit_interest | Taxa crédito à vista (uso futuro)
installment_credit_interest | Taxa crédito parcelado (uso futuro)
installment_debit_interest | Taxa débito parcelado (uso futuro)

Os campos marcados como "uso futuro" são campos presentes na modelagem mas que no momento não estão sendo usados na interface ou em relatórios.
