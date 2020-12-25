# PDVs

Um PDV representa o local físico onde são inseridas as vendas.

* Possui campo version: sim
* Possui campo original_id: não

## URL's

Produção: https://pdv-api.celero.mobi/pos.json

Método HTTP | Caminho | Descrição
--|--|--
GET | /pos.json | Consulta de PDVs. Utilize o parâmetro only_active=0 caso queira incluir os PDVs desativados.
GET | /pos/ID.json | Consulta
POST | /pos.json | Criação de um novo PDV.
PUT | /pos/ID.json | Alteração de um PDV.
DELETE | /pos/ID.json | Desativação de um PDV ("soft delete")

## Campos

Campo | Descrição
--|--
id | Identificador (apenas leitura)
number | Número do PDV dentro da loja. Atribuido automaticamente se omitido
global_order | Ordem global do PDV dentro do domain. Usado como ordenação na apresentação dos PDVs no sistema. Preenchido automaticamente se omitido.
label | Rótulo do PDV, usado em alguns relatórios e em algumas interfaces do usuário.
short_name | Nome curto da loja, usado em algumas interfaces do sistema para permitir uma melhor visualização das lojas
enable_web_sale | Se verdadeiro, não irá considerar como um PDV externo (desktop) e sim como um PDV que será usado no frontend via web.
