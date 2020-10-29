# Departamentos

Departamento é uma grande divisão da loja, por exemplo, 'Adulto', 'Infantil' e 'Cama, mesa e banho' podem ser considerados departamentos. São divisões do ponto de vista do cliente final. Seu uso é opcional.

* Possui campo version: sim
* Possui campo original_id: não

## URL's

Produção: https://pdv-api.celero.mobi/departments.json

Método HTTP | Caminho | Descrição
--|--|--
GET | /departments.json | Consulta de departamentos.
GET | /departments/ID.json | Consulta de um departamento.
POST | /departments.json | Criação de uma novo departamento.
PUT | /departments/ID.json | Alteração de departamento.

## Campos

Campo | Descrição
--|--
id | Identificador (apenas leitura)
nome | Nome do departamento.
