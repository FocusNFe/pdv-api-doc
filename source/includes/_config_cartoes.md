# Config. de Cartões

Esta seção descreve como buscar e configurar as informações de cartão por loja.

* Possui campo version: sim
* Possui campo original_id: não

Utilizamos a seguinte nomenclatura:

* card_company_config - Configuração sobre as credenciadoras (por Domain). Possui uma relação com o modelo enabled_card_brand que indica quais cartões são aceitos em cada loja.
* enabled_card_brand - Lista (por card_company_config) as bandeiras habilitadas por loja.
* card_infos - Consolidado por loja sobre quais os parâmetros para o card_brand e card_company que são aceitos. As configurações são definidas por bandeira e credenciadora. Sempre que um card_company_config é alterado, um card_info pode ser criado ou atualizado.

As operações descritas nesta seção se referem a todas as lojas do domínio. Não é feito filtro por loja.


## URL's

Produção: https://pdv-api.celero.mobi/card_companies_config.json

Método HTTP | Caminho | Descrição
--|--|--
GET | /card_companies_config.json | Consulta todas as configurações de credenciadoras
POST | /card_companies_config.json | Cria nova configuração de credenciadora
PUT | /card_companies_config.json | Altera configuração de credenciadora

## Campos

Campos | Descrição
--|--
id | Identificador do registro
active | Se esta configuração está ativa ou não
accepts_debit | Aceita débito?
accepts_installment_credit | Aceita crédito parcelado?
accepts_installment_debit | Aceita débito parcelado?
accepts_revolving_credit | Aceita crédito à vista?
max_num_installments | Número máximo de parcelas (crédito)
version | Versão da configuração
debit_interest | Taxa do débito (uso futuro)
revolving_credit_interest | Taxa crédito à vista (uso futuro)
installment_credit_interest | Taxa crédito parcelado (uso futuro)
installment_debit_interest | Taxa débito parcelado (uso futuro)

Os campos marcados como "uso futuro" são campos presentes na modelagem mas que no momento não estão sendo usados na interface ou em relatórios.

### Campos da lista enabled_card_brands_attributes

Campos | Descrição
--|--
id | Identificador do registro
store_id | ID da loja
card_brand_id | Bandeira aceita na loja
