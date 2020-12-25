# Lojas

Uma loja representa um estoque onde podem ser associados vários PDVs.

* Possui campo version: sim
* Possui campo original_id: não
* Ignora serial_number usado na autenticação

## URL's

Produção: https://pdv-api.celero.mobi/stores.json

Método HTTP | Caminho | Descrição
--|--|--
GET | /stores.json | Consulta de lojas. Utilize o parâmetro only_active=0 caso queira incluir as lojas desativadas.
GET | /stores/ID.json | Consulta
POST | /stores.json | Criação de uma nova loja.
PUT | /stores/ID.json | Alteração de uma loja.
DELETE | /stores/ID.json | Desativação de uma loja ("soft delete")

## Campos

Campo | Descrição
--|--
id | Identificador (apenas leitura)
name* | Nome da loja  
serial_number | Número de série. Utilizado como autenticação da API (apenas leitura)
short_name | Nome curto da loja, usado em algumas interfaces do sistema para permitir uma melhor visualização das lojas
global_order | Ordem global da loja dentro do domain. Usado como ordenação na apresentação das lojas no sistema. Preenchido automaticamente se omitido.

Outros campos e modelos são devolvidos no retorno de uma consulta, incluindo campos de tabelas associadas, como o PDV. Estes dados associados são usados na interface do usuário final


## Considerações sobre a criação de uma loja

A criação de uma loja cria registros associados:

* Cria o primeiro PDV da loja
* Cria o primeiro usuário do primeiro PDV
* Associa os usuários do domínio à nova loja criada

## Considerações sobre a chave do registro de uma loja

No retorno das consultas de uma loja, excepcionalmente é devolvida com a chave "f_store" ao invés da chave esperada "store". Isso acontece devido à palavra "store" que é reservada dentro do Ember (interface do usuário final).
