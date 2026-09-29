# Regras de Negocio

| ID | Descricao | Relacionado |
|---|---|---|
| RN-01 | Sao negociaveis acoes, ETFs e fundos imobiliarios. | RF-04, RF-05 |
| RN-02 | Somente o administrador cadastra investidores, cada investidor possui uma conta e uma carteira. | RF-01 |
| RN-03 | Somente investidores cadastrados e ativos acessam o sistema, com senha e MFA, apos 5 tentativas consecutivas incorretas de MFA, a conta eh bloqueada por 15 minutos. | RF-02, RNF-02 |
| RN-04 | Sao aceitas ordens a mercado e limitadas, sempre com quantidade inteira e positiva. | RF-05 |
| RN-05 | Uma ordem possui um dos status: CRIADA, VALIDADA, ENVIADA, EXECUTADA, REJEITADA, CANCELADA ou FALHA. | RF-09 |
| RN-06 | CRIADA para VALIDADA ou REJEITADA, VALIDADA para ENVIADA ou CANCELADA, ENVIADA para EXECUTADA, CANCELADA ou FALHA. EXECUTADA, REJEITADA, CANCELADA e FALHA sao status finais e nao podem ser alterados. | RF-09 |
| RN-07 | Ao ser validada, uma ordem de compra reserva o valor da ordem no saldo, e uma ordem de venda bloqueia a quantidade de ativos, a reserva eh liberada se a ordem for rejeitada, cancelada ou falhar. | RF-07, RF-08 |
| RN-08 | Eh proibido vender quantidade maior que a disponivel em carteira. | RF-08 |
| RN-09 | Cada investidor possui limite de valor por ordem e limite de exposicao diaria (soma das ordens do dia), definidos pelo administrador, investidor sem limites definidos nao pode enviar ordens. | RF-12, RF-13 |
| RN-10 | Ordens so sao aceitas em dias uteis, das 10h as 17h, fora desse horario a ordem eh rejeitada, e as consultas continuam disponiveis. | RF-14 |
| RN-11 | Antes de ser enviada, a ordem passa por saldo ou posicao, limite de risco e situacao do mercado, se falhar em qualquer uma, eh rejeitada com o motivo informado. | RF-07, RF-08, RF-13, RF-14, RF-15 |
| RN-12 | A ordem so pode ser cancelada enquanto estiver VALIDADA ou ENVIADA, se a Bolsa executar a ordem antes do cancelamento, o cancelamento eh negado e a ordem permanece EXECUTADA. | RF-06 |
| RN-13 | Duas ordens com a mesma chave de idempotencia dentro de 3600 segundos sao a mesma ordem, e so a primeira eh processada. | RNF-09 |
| RN-14 | Se a Bolsa nao responder em 1 segundo, o sistema tenta novamente ate 3 vezes, com intervalo de 1 segundo, esgotadas as tentativas, a ordem passa a FALHA, a reserva eh liberada e o investidor eh notificado. | RNF-11, RNF-12 |
| RN-15 | Com a Bolsa ou o provedor de cotacoes indisponiveis, novas ordens nao sao aceitas, cotacao com mais de 5 segundos de atraso eh considerada desatualizada e nao pode ser usada. | RNF-14, RNF-20 |
| RN-16 | O investidor eh notificado quando a ordem for executada, rejeitada, cancelada ou falhar, com o motivo quando houver. | RF-10 |
| RN-17 | Login, criacao, envio, execucao, rejeicao e cancelamento de ordens e alteracao de limites sao registrados e mantidos por no minimo 5 anos, que ninguem pode alterar ou apagar. | RF-11, RNF-17 |
| RN-18 | O administrador nao acessa os registros de auditoria, o auditor nao altera cadastros nem limites, e o investidor acessa somente os proprios dados. | RF-17, RNF-04 |
| RN-19 | O historico do investidor exibe todas as suas ordens com o status atual e eh mantido por no minimo 5 anos. | RF-16 |