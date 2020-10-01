# Produtos

Este recurso representa um produto ou um conjunto de produtos que diferem apenas pelo seus valores de grade. Uma grade é uma dimensão do produto que pode assumir um conjunto de valores. Um exemplo de grade é "cor", que define a cor do produto, que pode assumir os valores "azul, preto, verde ou vermelho". A definição das grades e valores possíveis deve ser feita antes de cadastrar o produto utilizando o recurso [dimensions](#Variações). Cada produto aceita no máximo 3 valores de grade. Desta maneira podemos cadastrar uma hierarquia como esta:

* Blusa feminina da marca ACME (Agrupador)
	1. Cor preta, tamanho P (Item de grade)
	2. Cor preta, tamanho M (Item de grade)
	3. Cor vermelha, tamanho P (Item de grade)
	4. Cor vermelha, tamanho M (Item de grade)


O produto é usado para representar tanto o agrupador quanto o item de grade. Isto é feito utilizando os seguintes campos:

### Agrupador

Campo | Descrição
--|--
id | Identificador do agrupador
use_dimentions | true (indica que utiliza grade)
dimension1_id | Identificador da dimensão 1
dimension2_id | Identificador da dimensão 2
dimension3_id | Identificador da dimensão 3

### Item de grade

Campo | Descrição
--|--
id | Identificador do item de grade
main_product_id | Identificador do produto agrupador
use_dimensions | false
dimension1_value_id | Valor da dimensão 1 definida pelo agrupador
dimension2_value_id | Valor da dimensão 2 definida pelo agrupador
dimension3_value_id | Valor da dimensão 3 definida pelo agrupador

Outros campos são copiados automaticamente do produto agrupador


## URL's

Produção: http://api.focuslojas.com.br/products

Método HTTP | Caminho | Descrição
--|--|--
GET | /products | Consulta todas as variações cadastradas.
POST | /products | Cria um novo produto.

## Campos

Tipo de valor | Campos | Descrição
--|--|--
int | id | Identificador do produto agrupador ou item de grade
string | code | Referência do produto
string | barcode | Código de barras
string | description* | Descrição do produto
int | supplier_id* | Identificador do fornecedor - Pode ser utilizado o campo original_supplier_id em substituição a este
int | department_id | Identificador da seção
int | collection_id | Identificador da coleção
bool | floating_quantities
bool | keep_separated
string | price_label | Rótulo de preço
string | measurement_unit | Unidade de medida
bool | ignore_stock_control | Informa se ignora controle de estoque
decimal | average_cost | Custo médio
decimal | price* | Preço
decimal | wholesale_price | Preço de atacado
bool | use_dimensions | Informa se utiliza valores de grade
int | main_product_id | (Apenas para itens de grade) Informa identificador do agrupador
int | product_type_id | Identificador do tipo de produto
int | dimension1_id | (Apenas para agrupador) Identificador da dimensão 1
int | dimension2_id | (Apenas para agrupador) Identificador da dimensão 2
int | dimension3_id | (Apenas para agrupador) Identificador da dimensão 3
int | dimension1_value_id | (Apenas para item de grade) Identificador do valor da dimensão 1
int | dimension2_value_id | (Apenas para item de grade) Identificador do valor da dimensão 2
int | dimension3_value_id | (Apenas para item de grade) Identificador do valor da dimensão 3
string | cfop_venda_dentro_estado | CFOP para venda dentro do estado
string | cfop_venda_fora_estado | CFOP para venda fora do estado
string | cfop_remessa_consignacao | CFOP para remessa de consignação
string | cfop_devolucao_consignacao | CFOP para devolução de consignação
string | cfop_venda_consig_dentro_estado | CFOP para venda consignada dentro do estado
string | cfop_venda_consig_fora_estado | CFOP para venda consignada fora do estado
string | cfop_devolucao_fornecedor_dentro | CFOP para devolução a fornecedor dentro do estado
string | cfop_devolucao_fornecedor_fora | CFOP para devolução a fornecedor fora do estado
string | capitulo_ncm | Capítudo da NCM
string | codigo_ncm_efetivo | Código da NCM
string | gtin | GTIN do produto, opcional.
string | gtin_efetivo | GTIN. Apenas leitura. Mostrará barcode se ele for um GTIN válido, caso contrário devolverá o campo GTIN. Se este também não estiver presente, devolve a string "SEM GTIN".
string | codigo_cest | Código CEST
int | icms_origem | Origem do produto, conforme regulamentação do ICMS: **0** - Nacional,**1** - Estrangeira - Importação direta,**2** - Estrangeira - Adquirida no mercado interno,**3** - Nacional com mais de 40% de conteúdo estrangeiro,**4** - Nacional - Processos Produtivos Básicos,**5** - Nacional com menos de 40% de conteúdo estrangeiro,**6** - Estrangeira por importação direta que não tem similar nacional,**7** - Estrangeira adquirida no mercado interno e que não tem similar nacional
string | active | Indica se cliente esta ativo ou não (default: verdadeiro)
string | IAT | Indicador de Arredondamento ou Truncamento
string | IPPT | Indicador de Produção Própria ou Terceirizada
boolean | adquirido_com_st | Indica se o produto foi adquirido com substituição tributária
string | codigo_beneficio_fiscal | 8 caracteres exatos. Indica o código do benefício fiscal para produtos não tributados, isentos ou imunes. Alguns estados não utilizam ainda este campo.

(\*) Indica campos obrigatórios.

## Criação

Para criar um novo cadastro de produto utilize a URL abaixo, alterando para o ambiente desejado (produção ou homologação).

`http://api.focuslojas.com.br/products`

Utilize o comando HTTP **POST** para enviar o cadastro para nossa API. Envie como corpo da requisição os dados em formato JSON, utilizando os campos listados na seção [Campos](#campos)

Ao lado você pode visualizar como é o JSON esperado para criação e como é o JSON devolvido pela API.

> Exemplo de JSON para criação de um produto.

```json
```

## Consulta

Para consultar todos os cadastros de variações utilize a URL abaixo, alterando para o ambiente desejado (produção ou homologação).

`http://api.focuslojas.com.br/products`

Utilize o comando HTTP **GET** nesta consulta. Os campos retornados serão os mesmos campos que foram listados no menu [Campos](#campos).

Ao lado você pode visualizar como é o JSON de resposta da nossa API.

> JSON enviado pela API Focus Lojas na consulta de todos os registros.

```json
```

## Erros