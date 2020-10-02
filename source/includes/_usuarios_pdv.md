# Usuários do PDV

Este recurso represente o cadastro de um usuário do PDV (vendedor, gerente ou administrador).

## URL's

Produção: http://api.focuslojas.com.br/pos_users

Método HTTP | Caminho | Descrição
--|--|--	
GET | /pos_users | Consulta de departamentos.
POST | /pos_users | Criação de uma novo departamento.

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

## Criação

Para criar um novo departamento utilize a URL abaixo, alterando para o ambiente desejado (produção ou homologação).

`http://api.focuslojas.com.br/pos_users`

Utilize o comando HTTP **POST** para enviar o cadastro para nossa API. Envie como corpo da requisição os dados em formato JSON, utilizando os campos listados abaixo.

Ao lado você pode visualizar como é o JSON esperado para criação e como é o JSON devolvido pela API.

> Exemplo de JSON para criação de um fornecedor.

```json
```

## Consulta

Para consultar os cadastros de usuários utilize a URL abaixo, alterando para o ambiente desejado (produção ou homologação).

`http://api.focuslojas.com.br/pos_users`

Utilize o comando HTTP **GET** nesta consulta. Os campos retornados serão os mesmos campos que foram listados no menu [Campos](#campos).

Ao lado você pode visualizar como é o JSON de resposta da nossa API.

> JSON enviado pela API Focus Lojas como resposta da consulta.

```json
```

## Erros	