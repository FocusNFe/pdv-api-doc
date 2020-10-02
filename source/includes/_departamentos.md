# Departamentos

Departamento é uma grande divisão da loja, por exemplo, 'Adulto', 'Infantil' e 'Cama, mesa e banho' pode ser considerados departamentos.

## URL's

Produção: http://api.focuslojas.com.br/departments

Método HTTP | Caminho | Descrição
--|--|--
GET | /departments | Consulta de departamentos.
POST | /departments | Criação de uma novo departamento.

## Campos

Campo | Descrição
--|--
nome | Nome do departamento.


## Criação

Para criar um novo departamento utilize a URL abaixo, alterando para o ambiente desejado (produção ou homologação).

`http://api.focuslojas.com.br/departments`

Utilize o comando HTTP **POST** para enviar o cadastro para nossa API. Envie como corpo da requisição os dados em formato JSON, utilizando os campos listados abaixo.

Ao lado você pode visualizar como é o JSON esperado para criação e como é o JSON devolvido pela API.

> Exemplo de JSON para criação de um departamento.

```json
```

## Consulta

Para consultar os cadastros de departamentos utilize a URL abaixo, alterando para o ambiente desejado (produção ou homologação).

`http://api.focuslojas.com.br/departments`

Utilize o comando HTTP **GET** nesta consulta. Os campos retornados serão os mesmos campos que foram listados no menu [Campos](#campos).

Ao lado você pode visualizar como é o JSON de resposta da nossa API.

> JSON enviado pela API Focus Lojas como resposta da consulta.

```json
```

## Erros	