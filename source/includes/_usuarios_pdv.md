# Usuários do PDV

Este recurso represente o cadastro de um usuário do PDV (vendedor, gerente ou administrador). Uma venda possui necessariamente um usuário do PDV (representando o vendedor).

* Possui campo version: sim
* Possui campo original_id: não

## URL's

Produção: http://celero.focuslojas.com.br/pos_users.json

Método HTTP | Caminho | Descrição
--|--|--
GET | /pos_users.json | Consulta
GET | /pos_users/ID.json | Consulta de registro específico
POST | /pos_users.json | Criação de um novo registro
PUT | /pos_users/ID.json | Alteração de um registro

## Campos

Tipo de valor | Campo | Descrição
--|--|--
int | id - Identificador do sistema.
string | name* | Nome do usuário - É utilizado como chave de atualização, veja os comentários na operação create.
string | login* | Login do usuário, utilizado para acessar o sistema.
string | password | Senha do usuário, assume o valor "123" se não informado.
int) code | Código do usuário, criado automaticamente se não informado.
string) cpf | CPF do usuário.
bool | is_admin | Indica se o usuário é um administrador (terá acesso total ao PDV em todas as lojas).
bool | is_manager | Indica se o usuário é um gerente (terá acesso total ao PDV apenas na loja especificada).
bool | is_salesperson | Indica se o usuário é um vendedor (terá acesso limitado ao PDV apenas na loja especificada).
bool | is_cash_drawer_operator | Indica se o usuário é um caixa (poderá abrir e operar um caixa).
bool | active | Indica se o usuário esta ativo.

(\*) Campos obrigatórios.
