# Informações de contato

Este recurso representa as informações de contato de uma pessoa ou empresa (Cliente ou Fornecedor). Cada pessoa pode ter de zero à N contatos. O uso deste endpoint é opcional, pois ele estes registros podem ser cadastrados diretamente no cadastro de cliente ou fornecedor.

## URL's

Produção: http://api.focuslojas.com.br/contact_infos

Método HTTP | Caminho | Descrição
--|--|--
GET | /contact_infos | Consulta de contatos.
POST | /contact_infos | Criação de uma novo contato.

## Campos

Tipo de valor | Campo | Descrição
--|--|--
int | id | Identificador do sistema.
int | person_id | id da pessoa no sistema.
string | contact_type* | Tipo do contato ("phone", "email", "fax", "cellphone", "person", "other").
string | value* | Valor do contato, exemplos (4199999389, suporte@acras.com.br, João, etc) dependendo do tipo.
string | comment | Observações deste contato.
integer | version | Versão do registro para buscas por registros atualizados.

(\*) Campos obrigatórios.

## Criação

Para criar um novo departamento utilize a URL abaixo, alterando para o ambiente desejado (produção ou homologação).

`http://api.focuslojas.com.br/contact_infos`

Utilize o comando HTTP **POST** para enviar o cadastro para nossa API. Envie como corpo da requisição os dados em formato JSON, utilizando os campos listados abaixo.

Ao lado você pode visualizar como é o JSON esperado para criação e como é o JSON devolvido pela API.

> Exemplo de JSON para criação de um contato.

```json
```

## Consulta

Para consultar os cadastros de departamentos utilize a URL abaixo, alterando para o ambiente desejado (produção ou homologação).

`http://api.focuslojas.com.br/contact_infos`

Utilize o comando HTTP **GET** nesta consulta. Os campos retornados serão os mesmos campos que foram listados no menu [Campos](#campos).

Ao lado você pode visualizar como é o JSON de resposta da nossa API.

> JSON enviado pela API Focus Lojas como resposta da consulta.

```json
```

## Erros
