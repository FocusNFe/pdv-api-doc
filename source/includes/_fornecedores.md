# Fornecedores

Este recurso represente o cadastro de um fornecedor. Cada produto possui necessariamente um fornecedor, também é usado para representar a marca do produto. Seu uso é obrigatório, mas ao criar uma rede de loja é criado um fornecedor default cujo nome é o nome da rede de lojas.

* Possui campo version: sim
* Possui campo original_id: sim

## URL's

Produção: https://pdv-api.celero.mobi/suppliers.json

Método HTTP | Caminho | Descrição
--|--|--
GET | /suppliers.json | Consulta
GET | /suppliers/ID.json | Consulta de registro específico
POST | /suppliers.json | Criação de um novo registro
PUT | /suppliers/ID.json | Alteração de um registro

## Campos

Tipo de valor | Campo | Descrição
--|--|--
int | id | Identificador do sistema.
int | original_id | Identificador externo.
string | legal_type* | "LEGAL" para pessoa jurídica ou "NATURAL" para pessoa física.
string | name* | Nome, se pessoa física, ou nome fantasia, para pessoa jurídica.
string | cnpj | CNPJ, apenas para pessoas jurídicas.
string | cpf | CPF, apenas para pessoas físicas.
string | inscricao_estadual | Inscrição estadual, apenas para pessoas jurídicas.
bool | isento_inscricao_estadual | Informa se a pessoa jurídica é isenta da inscrição estadual.
string | cep | CEP.
string | contact_name | Nome do contato, apenas para pessoas jurídicas.
string | rg | R.G., apenas para pessoas físicas.
string | razao_social | Razão social, apenas para pessoas jurídicas.
string | brand_name* | Nome da marca que o fornecedor representa.
string | web_address | Endereço da página web do fornecedor.
