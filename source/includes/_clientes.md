# Clientes

## URL's

Produção: http://api.focuslojas.com.br/customers.json

Método HTTP | Caminho | Descrição
--|--|--
POST | /customers.json | Cria um novo cadastro de cliente.
GET | /customers.json | Consulta de todos os clientes cadastrados.
GET | / customers/ID.json | Consulta um cadastro especifico.

## Campos

Abaixo descrevemos todos os campos possíveis para criação, consulta ou alteração de cadastro de clientes.

Inicialmente, vamos considerar os campos presentes na estrutura raíz do JSON, onde serão encontrados os arrays abaixo:

> Exemplo de como os campos são exibidos na raíz do JSON (omitimos os valores dos arrays):

```json

{
    "contact_infos": [],
    "addresses": [],
    "pais": [],
    "municipio": [],
    "installment_credits": [],
    "related_people": [],
    "contracts": [],
    "customer": {}
}

```

Grupo / Lista | Descrição
--|--
contact_infos | Lista de informações de contato (ver contact_infos).
addresses | Lista com os dados do endereço (ver addresses).
installment_credits |
related_people |
contracts |
pais | Lista com as informações do(s) país().
municipio | Lista com os dados do(s) município(s).
customers | Lista com os dados do(s) cliente(s).
meta | Mostra o campo 'total' com o total de registros encontrados (busca por todos os cadastros).


### Campos da lista contact_infos

Este grupo de campos armazena os dados dos contatos de um cliente, retornando as seguintes informações nas consultas:

```json
 "contact_infos": [
        {
            "id": 2416600,
            "value": "seu-email@email.com",
            "comment": null,
            "contact_type": "email"
        },
        {
            "id": 2418501,
            "value": "",
            "comment": "",
            "contact_type": "phone"
        }
    ]
```

Campo | Descrição
--|--
id | Número de identificação único para este registro.
value | Valor referente ao tipo de contato cadastrado.
comment | Comentário sobre este contrato.
contact_type | Tipo do contato, podendo ser: **email**, **cellphone**, **phone**, **fax** ou **other**.


### Campos da lista addresses

Este grupo de campos armazena os dados do endereço do cliente, retornando as seguintes informações nas consultas:


```json
"addresses": [
        {
            "id": 1597842,
            "logradouro": "Avenida interventor Manoel ribas",
            "numero": "170",
            "complemento": "",
            "bairro": "Centro",
            "cep": "86600137",
            "address_type": "default",
            "person_id": 1122790,
            "domain_id": 3572,
            "pais_id": 30,
            "municipio_id": 4052
        }
    ]
```

Campo | Descrição
--|--
id | Número de identificação único para este registro.
logradouro | Logradouro.
numero | Número do logradouro.
complemento | Complemento do endereço.
bairro | Bairro.
cep | CEP.
address_type | Tipo do endereço.
person_id | Número de identificação único do cliente.
domain_id | Número de itenficação único da loja.
pais_id | Número de itenficação único do país.
municipio_id | Número de itenficação único do município.


### Campos da lista pais

Este grupo de campos armazena os dados do país do cliente, retornando as seguintes informações nas consultas:

```json
"pais": [
        {
            "id": 30,
            "nome": "BRASIL"
        }
    ]
```

Campo | Descrição
--|--
id | Número de identificação único para este registro.
nome | Nome do país.

### Campos da lista municipio

Este grupo de campos armazena os dados do município do cliente, retornando as seguintes informações nas consultas:

```json
"municipio": [
        {
            "id": 4052,
            "nome_uf": "Paraná",
            "sigla_uf": "PR",
            "nome_municipio": "Rolândia",
            "nome_and_uf": "Rolândia - PR",
            "codigo_municipio": "4122404",
            "item_lista_servico_type": null
        }
    ]
```

Campo | Descrição
--|--
id | Número de identificação único para este registro.
nome_uf | Nome por extensão do Estado.
sigla_uf | Sigla do Estado.
nome_municipio | Nome da cidade.
nome_and_uf | Nome da cidade e sigla da UF, separados por um traço.
codigo_municipio | Código da cidade com base nos dados do IBGE.
item_lista_servico_type | Tipo do código do serviço, para NFSe, utilizados no município.


### Campos da lista installment_credits


### Campos da lista related_people


### Campos da lista contracts



### Campos da lista customers

Este grupo de campos armazena os dados do cliente, retornando as seguintes informações nas consultas:


```json
"customer": {
        "id": 1122790,
        "active": true,
        "cep": null,
        "cnpj": "99997942000185",
        "cnpj_emissao": "",
        "comment": null,
        "contact_name": "",
        "cpf": "",
        "inscricao_estadual": "9999825072",
        "inscricao_estadual_emissao": "",
        "inscricao_municipal": "",
        "inscricao_suframa": "",
        "isento_inscricao_estadual": false,
        "isento_inscricao_estadual_emissao": false,
        "legal_type": "LEGAL",
        "name": "T. Boito e Rigolton ME",
        "razao_social": "T. Boito e Rigolton ME",
        "regime_simples_nacional": false,
        "rg": "",
        "web_address": null,
        "f_store_id": null,
        "birthday": null,
        "special": false,
        "operator_message": "",
        "blocked": false,
        "reason_blocked": "",
        "gender": "",
        "created_at": "2019-08-14T14:05:50-03:00",
        "updated_at": "2019-08-14T14:05:50-03:00",
        "version": 11934,
        "enable_installment_credit": false,
        "nfe_address_uf": "PR",
        "name_and_document": "T. Boito e Rigolton ME 21.987.942/0001-85",
        "contact_info_ids": [
            2412500,
            2412501
        ],
        "address_ids": [
            1597842
        ],
        "sale_type_id": null,
        "store_id": null,
        "installment_credit_id": null,
        "related_person_ids": [],
        "saas_price_id": null,
        "contract_ids": []
    }
```

Tipo de valor | Campo | Descrição
--|--|--
int | id | Identificador do sistema.
string | active | Indica se cliente esta ativo ou não (padrão: verdadeiro).
string | cep | CEP.
string | cnpj | CNPJ, apenas para pessoas jurídicas.
 | cnpj_emissao | 
 | comment |
string | contact_name | Nome do contato, apenas para pessoas jurídicas.
string | cpf | CPF, apenas para pessoas físicas.
string | inscricao_estadual | Inscrição estadual, apenas para pessoas jurídicas.
 | inscricao_estadual_emissao |
 | inscricao_municipal |
 | inscricao_suframa |
bool | isento_inscricao_estadual | Informa se a pessoa jurídica é isenta da inscrição estadual.
bool | isento_inscricao_estadual_emissao | 
string | legal_type | "LEGAL" para pessoa jurídica ou "NATURAL" para pessoa física.
string | name | Nome, se pessoa física, ou nome fantasia, para pessoa jurídica.
string | razao_social | Razão social, apenas para pessoas jurídicas.
bool | regime_simples_nacional | Indicador se o cliente é do Regime Tributário Simples Nacional.
string | rg | R.G., apenas para pessoas físicas.
 | web_address |
 | f_store_id |
date | birthday | Data de aniversário, se pessoa física.
bool | special | Informa se é cliente especial.
text | operator_message | Mensagem ao operador.
bool | blocked | Informa se este cliente esta bloqueado.
text | reason_blocked | Se bloqueado, informa a razão.
string | gender | "M" para masculino e "F" para feminino, se pessoa física.
date | created_at | Data de criação do cadastro.
date | updated_at | Data da última alteração no cadastro.
int | version | Número da versão do cadastro.
bool | enable_installment_credit |
 | nfe_address_uf |
string | name_and_document | Nome do cliente e seu documento de identificação (CNPJ ou CPF).
array | contact_info_ids | Código de referência dos contatos do cliente.
array | address_ids | Código de referência do endereço.
 | sale_type_id |
int | store_id | Identificador interno (no retaguarda) da loja de origem do cliente
 | installment_credit_id |
 | related_person_ids |
 | saas_price_id |


## Criação

Para criar um novo cadastro de cliente utilize a URL abaixo, alterando para o ambiente desejado (produção ou homologação).

`http://api.focuslojas.com.br/customers.json`

Utilize o comando HTTP **POST** para enviar o cadastro para nossa API. Envie como corpo da requisição os dados em formato JSON, utilizando os campos listados na seção [Campos](#campos)

Ao lado você pode visualizar como é o JSON esperado para criação e como é o JSON devolvido pela API.

> Exemplo de JSON para criação de um cliente.

```json
{
    "customer":
    {
        "name": "Esplugão de homologacao",
        "legal_type":"NATURAL",
        "cpf":"88127738000",
        "birthday":"1992-06-05",
        "addresses_attributes":
        [
            {
                "address_type": "default",
                "logradouro": "Rua da cascatinha",
                "numero": 138,
                "bairro": "acacias",
                "cep":"83550020"
            }
        ]
    } 
}
```

> Exemplo da resposta da API para criação de cliente:

```json
{
    "contact_infos": [],
    "addresses": [],
    "installment_credits": [],
    "related_people": [],
    "contracts": [],
    "customer": {
        "id": 1352148,
        "active": true,
        "cep": null,
        "cnpj": null,
        "cnpj_emissao": null,
        "comment": null,
        "contact_name": null,
        "cpf": null,
        "inscricao_estadual": null,
        "inscricao_estadual_emissao": null,
        "inscricao_municipal": null,
        "inscricao_suframa": null,
        "isento_inscricao_estadual": false,
        "isento_inscricao_estadual_emissao": null,
        "legal_type": "NATURAL",
        "name": "Nome do usuário",
        "razao_social": null,
        "regime_simples_nacional": false,
        "rg": null,
        "web_address": null,
        "f_store_id": null,
        "birthday": null,
        "special": null,
        "operator_message": null,
        "blocked": null,
        "reason_blocked": null,
        "gender": null,
        "created_at": "2020-09-30 11:04:29 -0300",
        "updated_at": "2020-09-30 11:04:29 -0300",
        "version": 13226,
        "enable_installment_credit": false,
        "nfe_address_uf": null,
        "name_and_document": "Nome do usuário",
        "contact_info_ids": [],
        "address_ids": [],
        "sale_type_id": null,
        "store_id": null,
        "installment_credit_id": null,
        "related_person_ids": [],
        "saas_price_id": null,
        "contract_ids": []
    }
}
```

## Consulta

Há duas formas de consultar os cadastros de clientes, a primeira é realizando um consulta de todos os registros, a segunda forma é a consulta de um cadastro especifico.

### Consultando todos os cadastros

Para consultar todos os cadastros de clientes utilize a URL abaixo, alterando para o ambiente desejado (produção ou homologação).

`http://api.focuslojas.com.br/customers.json`

Utilize o comando HTTP **GET** nesta consulta. Os campos retornados serão os mesmos campos que foram listados no menu [Campos](#campos).

Ao lado você pode visualizar como é o JSON de resposta da nossa API.

> JSON enviado pela API Focus Lojas como resposta da consulta.

```json
{
    "contact_infos": [],
    "addresses": [        
        {
            "id": 1743730,
            "logradouro": "Albert Street",
            "numero": "3640",
            "complemento": null,
            "bairro": "Saskatchewan",
            "cep": "00000000",
            "address_type": "default",
            "person_id": 1249678,
            "domain_id": 13322,
            "pais_id": 39,
            "municipio_id": 5565
        },
        {
            "id": 1743734,
            "logradouro": "Alameda Arapoema",
            "numero": "659",
            "complemento": null,
            "bairro": "Tamboré",
            "cep": "06460080",
            "address_type": "default",
            "person_id": 1249735,
            "domain_id": 13322,
            "pais_id": 30,
            "municipio_id": 3866
        }
    ],
    "pais": [
        {
            "id": 30,
            "nome": "BRASIL"
        },
        {
            "id": 39,
            "nome": "CANADA"
        }
    ],
    "municipio": [
        {
            "id": 5565,
            "nome_uf": "EXTERIOR",
            "sigla_uf": "EX",
            "nome_municipio": "EXTERIOR",
            "nome_and_uf": "EXTERIOR - EX",
            "codigo_municipio": "9999999",
            "item_lista_servico_type": null
        },
        {
            "id": 3866,
            "nome_uf": "São Paulo",
            "sigla_uf": "SP",
            "nome_municipio": "Barueri",
            "nome_and_uf": "Barueri - SP",
            "codigo_municipio": "3505708",
            "item_lista_servico_type": null
        }
    ],
    "installment_credits": [],
    "related_people": [],
    "contracts": [],
    "customers": [        
        {
            "id": 1249678,
            "active": true,
            "cep": null,
            "cnpj": null,
            "cnpj_emissao": null,
            "comment": null,
            "contact_name": null,
            "cpf": "",
            "inscricao_estadual": null,
            "inscricao_estadual_emissao": null,
            "inscricao_municipal": null,
            "inscricao_suframa": null,
            "isento_inscricao_estadual": false,
            "isento_inscricao_estadual_emissao": null,
            "legal_type": "NATURAL",
            "name": "NF-E EMITIDA EM AMBIENTE DE HOMOLOGACAO - SEM VALOR FISCAL",
            "razao_social": null,
            "regime_simples_nacional": false,
            "rg": null,
            "web_address": null,
            "f_store_id": null,
            "birthday": null,
            "special": null,
            "operator_message": null,
            "blocked": null,
            "reason_blocked": null,
            "gender": null,
            "created_at": "2020-04-06T11:27:02-03:00",
            "updated_at": "2020-04-07T09:25:52-03:00",
            "version": 859,
            "enable_installment_credit": false,
            "nfe_address_uf": "EX",
            "name_and_document": "NF-E EMITIDA EM AMBIENTE DE HOMOLOGACAO - SEM VALOR FISCAL",
            "contact_info_ids": [],
            "address_ids": [
                1743730
            ],
            "sale_type_id": null,
            "store_id": null,
            "installment_credit_id": 11841098,
            "related_person_ids": [],
            "saas_price_id": null,
            "contract_ids": []
        },
        {
            "id": 1249735,
            "active": true,
            "cep": null,
            "cnpj": "42581280000976",
            "cnpj_emissao": null,
            "comment": null,
            "contact_name": null,
            "cpf": null,
            "inscricao_estadual": "206260006117",
            "inscricao_estadual_emissao": null,
            "inscricao_municipal": null,
            "inscricao_suframa": null,
            "isento_inscricao_estadual": false,
            "isento_inscricao_estadual_emissao": null,
            "legal_type": "LEGAL",
            "name": "NF-E EMITIDA EM AMBIENTE DE HOMOLOGACAO - SEM VALOR FISCAL",
            "razao_social": "NF-E EMITIDA EM AMBIENTE DE HOMOLOGACAO - SEM VALOR FISCAL",
            "regime_simples_nacional": false,
            "rg": null,
            "web_address": null,
            "f_store_id": null,
            "birthday": null,
            "special": null,
            "operator_message": null,
            "blocked": null,
            "reason_blocked": null,
            "gender": null,
            "created_at": "2020-04-06T15:02:25-03:00",
            "updated_at": "2020-04-06T15:24:41-03:00",
            "version": 858,
            "enable_installment_credit": false,
            "nfe_address_uf": "SP",
            "name_and_document": "NF-E EMITIDA EM AMBIENTE DE HOMOLOGACAO - SEM VALOR FISCAL 42.581.280/0009-76",
            "contact_info_ids": [],
            "address_ids": [
                1743734
            ],
            "sale_type_id": null,
            "store_id": null,
            "installment_credit_id": 11841166,
            "related_person_ids": [],
            "saas_price_id": null,
            "contract_ids": []
        }
    ],
    "meta": {
        "total": 2
    }
}
```


### Consultando um cadastro especifico

Para consultar um cadastro de cliente especifico utilize a URL abaixo, alterando para o ambiente desejado (produção ou homologação).

`http://api.focuslojas.com.br/customers/ID.json`

Utilize o comando HTTP **GET** nesta consulta. Os campos retornados serão os mesmos campos que foram listados no menu [Campos](#campos).

Ao lado você pode visualizar como é o JSON de resposta da nossa API.

> JSON enviado pela API Focus Lojas como resposta da consulta.

```json
{
    "contact_infos": [
        {
            "id": 2412500,
            "value": "seu-email@email.com",
            "comment": null,
            "contact_type": "email"
        },
        {
            "id": 2412501,
            "value": "",
            "comment": null,
            "contact_type": "phone"
        }
    ],
    "addresses": [
        {
            "id": 1597842,
            "logradouro": "Avenida interventor Manoel ribas",
            "numero": "170",
            "complemento": "",
            "bairro": "Centro",
            "cep": "86600137",
            "address_type": "default",
            "person_id": 1122790,
            "domain_id": 3572,
            "pais_id": 30,
            "municipio_id": 4052
        }
    ],
    "pais": [
        {
            "id": 30,
            "nome": "BRASIL"
        }
    ],
    "municipio": [
        {
            "id": 4052,
            "nome_uf": "Paraná",
            "sigla_uf": "PR",
            "nome_municipio": "Rolândia",
            "nome_and_uf": "Rolândia - PR",
            "codigo_municipio": "4122404",
            "item_lista_servico_type": null
        }
    ],
    "installment_credits": [],
    "related_people": [],
    "contracts": [],
    "customer": {
        "id": 1122790,
        "active": true,
        "cep": null,
        "cnpj": "99997942000185",
        "cnpj_emissao": "",
        "comment": null,
        "contact_name": "",
        "cpf": "",
        "inscricao_estadual": "9069999072",
        "inscricao_estadual_emissao": "",
        "inscricao_municipal": "",
        "inscricao_suframa": "",
        "isento_inscricao_estadual": false,
        "isento_inscricao_estadual_emissao": false,
        "legal_type": "LEGAL",
        "name": "T. Boito e Rigolton ME",
        "razao_social": "T. Boito e Rigolton ME",
        "regime_simples_nacional": false,
        "rg": "",
        "web_address": null,
        "f_store_id": null,
        "birthday": null,
        "special": false,
        "operator_message": "",
        "blocked": false,
        "reason_blocked": "",
        "gender": "",
        "created_at": "2019-08-14T14:05:50-03:00",
        "updated_at": "2019-08-14T14:05:50-03:00",
        "version": 11934,
        "enable_installment_credit": false,
        "nfe_address_uf": "PR",
        "name_and_document": "T. Boito e Rigolton ME 21.987.942/0001-85",
        "contact_info_ids": [
            2412500,
            2412501
        ],
        "address_ids": [
            1597842
        ],
        "sale_type_id": null,
        "store_id": null,
        "installment_credit_id": null,
        "related_person_ids": [],
        "saas_price_id": null,
        "contract_ids": []
    }
}
```

## Erros

Erros mais comuns e possíveis foram documentados aqui como uma forma de auxiliar / orientar os novos usuários da nossa API. Separamos os erros possíveis conforme o método HTTP utilizado.

### Criação (POST)

### Consulta (GET)

Abaixo temos a tabela dos erros mais comuns quando a operação é a consulta de clientes.

Código HTTP | Mensagem | Causa | Correção
--|--|--|--
401 (Unauthorized) | `{ "error": "Você precisa logar-se ou cadastrar-se antes de continuar." }` | Header de autenticação não informado. | É necessário informar o header de autenticação.
401 (Unauthorized) | ` HTTP Token: Access denied. ` | Header de autenticação informado incorretamente. | Informe o header de autenticação confome o esperado. Veja [aqui](#autenticacao).

### Exclusão (DELETE)

### Alteração (PUT)