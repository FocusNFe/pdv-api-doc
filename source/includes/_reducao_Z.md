# Redução Z

Este recurso representa o registro das reduções z armazenados na impressora fiscal. Recuperamos os dados exatamente como eles estão na impressora, com zeros a esquerda e quantidade fixa de posições (as duas últimas representam os centavos).

## URL's

Produção: http://api.focuslojas.com.br/reducoes_z

Método HTTP | Caminho | Descrição
--|--|--	
GET | /reducoes_z | Consulta de departamentos.
POST | /reducoes_z | Criação de uma novo departamento.

## Campos

Campo | Descrição
--|--
data_movimento | Data dos movimentos.
modo | Modo.
cont_reinicio_operacao | Contador de reinício de operações.
cont_reducao_z | Contador de reduções Z.
cont_ordem_operacao | Contador de ordem de operação.
cont_geral_oper_nao_fiscais | Contador geral de operações não fiscais.
cont_cupom_fiscal | Contador de cupom fiscal.
cont_geral_rel_ger | Contador geral de relatórios gerenciais.
cont_fita_detalhe_emitida | Contador de fita detalhe emitida.
cont_oper_nao_fiscais_canceladas | Contador de operações não fiscais canceladas.
cont_cupom_fiscal_cancelados | Contador de cupons fiscais cancelados.
cont_operacaoes_nao_fiscais | Contador de operações não fiscais.
cont_especificos_rel_ger | Contador específicicos de relatório gerencial.
cont_comp_deb_cred | Contador de comprovantes de débito/crédito.
cont_comp_deb_cred_nao_emitido | Contador de comprovantes de débito/crédito não emitidos.
cont_comp_deb_cred_cancelados | Contador de comprovantes de débito/crédito cancelados.
tot_geral | Total Geral.
tot_isencao_icms | Total de isenção do ICMS.
tot_nao_incidencia_icms | Total de não incidência do ICMS.
tot_subst_trib_icms | Total de substituição tributára do ICMS.
tot_isencao_issqn | Total de isenção do ISSQN.
tot_nao_incidencia_issqn | Total de não incidência do ISSQN.
tot_subst_trib_issqn | Total de substituição tributária do ISSQN.
tot_descontos_icms | Total de descontos do ICMS.
tot_descontos_issqn | Total de descontos do ISSQN.
tot_acrescimos_icms | Total de acréscimos do ICMS.
tot_acrescimos_issqn | Total de acréscimos do ISSQN.
tot_cancelamentos_icms | Total de cancelamentos do ICMS.
tot_cancelamentos_issqn | Total de cancelamentos do ISSQN.
tot_parc_nao_sujeitos_icms | Vetor com totais parciais não sujeitos ao ICMS (sequências de 14 posições).
tot_sangria | Total de sangria.
tot_suprimento | Total de suprimento.
tot_cancelamentos_nao_fiscais | Total de cancelamentos não fiscais.
tot_descontos_nao_fiscais | Total de descontos não fiscais.
tot_acrescimos_nao_fiscais | Total de acréscimos não fiscais.
data_hora_reducao | Data e hora em que foi feita a redução Z.
tot_geral_inicial | Campo calculado já em formato decimal - É o totalizador geral no início do dia (igual ao totalizador geral do fim do dia anterior).
tot_geral_final | Campo calculado já em formato decimal - É o totalizador geral no final do dia (igual ao totalizador geral).
venda_bruta | Campo calculado já em formato decimal - É a venda bruta, calculada como tot_geral_final - tot_geral_inicial.
numero_mapa_fiscal | Número do mapa fiscal.
pos | Lista com informações do PDV/ECF.
info_aliquotas | Lista de informações sobre as alíquotas e totais parciais.
	
### Campos da lista pos

Informações do PDV/ECF.

Campo | Descrição
--|--
id | Identificador do banco de dados.
number | Número.
ecf_serial_number | Número de série do ECF.

### Campos da lista info_aliquotas

Informações com todas as alíquotas e totais parciais.

Campo | Descrição
--|--
tot_parcial | Total parcial (Base de cálculo).
aliq_trib | Allíquota tributária.
valor_imposto | Valor do imposto.


## Consulta

Para consultar os cadastros de usuários utilize a URL abaixo, alterando para o ambiente desejado (produção ou homologação).

`http://api.focuslojas.com.br/reducoes_z`

Utilize o comando HTTP **GET** nesta consulta. Os campos retornados serão os mesmos campos que foram listados no menu [Campos](#campos).

Ao lado você pode visualizar como é o JSON de resposta da nossa API.

> JSON enviado pela API Focus Lojas como resposta da consulta.

```JSON
```

## Erros	