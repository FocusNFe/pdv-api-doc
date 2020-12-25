# Domains

Um domain representa uma coleção de lojas pertencentes a um mesmo proprietário (ex: uma rede de lojas).

* Possui campo version: não
* Possui campo original_id: não
* Ignora serial_number usado na autenticação
* API disponível apenas com token master

## URL's

Produção: https://pdv-api.celero.mobi/domains.json

Método HTTP | Caminho | Descrição
--|--|--
GET | /domains.json | Consulta de domains. Utilize o parâmetro only_active=0 caso queira incluir os domínios desativados.
GET | /domains/ID.json | Consulta de um domain.
POST | /domains.json | Criação de uma novo domain.
PUT | /domains/ID.json | Alteração de domain.
DELETE | /domains/ID.json | Desativação de um domain ("soft delete")

## Campos

Campo | Descrição
--|--
id | Identificador (apenas leitura)
name* | Nome do domain
first_user_email* | Email do primeiro usuário. Disponível apenas na criação do domain, quando informado é criado um usuário com uma senha default e enviado para o seu email. Caso o usuário já exista ele é apenas associado ao domain.

Outros campos e modelos são devolvidos no retorno de uma consulta, incluindo campos de tabelas associadas, como lojas, fornecedores, variações e modelos de etiquetas. Estes dados associados são usados na interface do usuário final


## Considerações sobre a criação de um domain

A criação de um domain cria registros associados:

* Cria a primeira loja
* Cria o primeiro PDV para a primeira loja  
* Cria o primeiro usuário do primeiro PDV
* Cria o usuário administrador caso ele ainda não exista

Todos estes registros são devolvidos na criação de um novo domain.
