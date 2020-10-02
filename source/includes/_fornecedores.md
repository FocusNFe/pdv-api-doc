# Fornecedores

Este recurso represente o cadastro de um fornecedor.

## URL's

Produção: http://api.focuslojas.com.br/suppliers

Método HTTP | Caminho | Descrição
--|--|--
GET | /suppliers | Consulta de departamentos.
POST | /suppliers | Criação de uma novo departamento.

## Campos

Tipo de valor | Campo | Descrição
--|--|--
int | id | Identificador do sistema.
int | original_id | Identificador externo.
string | legal_type | "legal" para pessoa jurídica ou "natural" para pessoa física.
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


## Criação

Para criar um novo departamento utilize a URL abaixo, alterando para o ambiente desejado (produção ou homologação).

`http://api.focuslojas.com.br/suppliers`

Utilize o comando HTTP **POST** para enviar o cadastro para nossa API. Envie como corpo da requisição os dados em formato JSON, utilizando os campos listados abaixo.

Ao lado você pode visualizar como é o JSON esperado para criação e como é o JSON devolvido pela API.

> Exemplo de JSON para criação de um fornecedor.

```json
```

## Consulta

Para consultar os cadastros de departamentos utilize a URL abaixo, alterando para o ambiente desejado (produção ou homologação).

`http://api.focuslojas.com.br/suppliers`

Utilize o comando HTTP **GET** nesta consulta. Os campos retornados serão os mesmos campos que foram listados no menu [Campos](#campos).

Ao lado você pode visualizar como é o JSON de resposta da nossa API.

> JSON enviado pela API Focus Lojas como resposta da consulta.

```json
```

## Erros	