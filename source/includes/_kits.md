# Kits

Este recurso representa o cadastro de um kit de produtos. Seu uso é opcional.

* Possui campo version: sim
* Possui campo original_id: sim

## URL's

Produção: http://celero.focuslojas.com.br/kits.json

Método HTTP | Caminho | Descrição
--|--|--
GET | /kits.json | Consulta
GET | /kits/ID.json | Consulta de registro específico
POST | /kits.json | Criação de um novo registro
PUT | /kits/ID.json | Alteração de um registro

## Campos

Tipo de valor | Campo | Descrição
--|--|--
int | id | Identificador do sistema.
int | original_id | Identificador externo.
string | code | Referência do kit (será criada automaticamente se não informada).
string | barcode | Código de barras do kit (será criado automaticamente se não informadao).
string | name* | Nome do kit.
bool | active* | Indica se o kit esta ativo ou não.
array| items_attributes* | Lista de items que compõe o produto. Cada item do array pode conter os campos abaixo.

### Campos da lista items_attributes

Tipo de valor | Campo | Descrição
--|--|--
int | product_id** - Referência do produto - Pode ser substituído pelo campo original_product_id
int | supplier_id** - Referência do fornecedor
str | code** - referência do produto
int | quantity* - Quantidade do produto
decimal| price* - Preço do produto

(\*) Campos obrigatórios.

Para identificação do produto que compõe o kit pode ser informado o **product_id**, o **original_product_id** ou o par code e **supplier_id**.

## Observações

Sempre que um kit for atualizado deverá ser passado novamente todos os itens que compõe o kit. O sistema irá verificar se houve diferença entre os itens e irá desativar automaticamente os itens que não existem mais.
