# Criterios de Aceitacao

| ID | Criterio | Relacionado |
|---|---|---|
| CA-01 | Dado um administrador autenticado, quando ele cadastra um investidor com dados validos, sua conta e sua carteira sao criados e o evento eh registrado na auditoria. | RF-01, RN-02 |
| CA-02 | Dado um investidor com senha correta, quando ele informa um codigo MFA valido, entao o acesso eh concedido; se o codigo for invalido, o acesso eh negado. | RF-02 |
| CA-03 | Dado um investidor com 5 codigos MFA incorretos consecutivos, quando ele tenta uma sexta vez, entao a conta permanece bloqueada por 15 minutos. | RN-03, RNF-02 |
| CA-04 | Dado um investidor autenticado, quando ele consulta a carteira, entao o sistema exibe seu saldo e seus ativos, e nenhum dado de outro investidor. | RF-03, RNF-04 |
| CA-05 | Dado que o provedor esta disponivel, quando o investidor consulta cotacoes, entao as cotacoes exibidas tem no maximo 5 segundos de atraso. | RF-04, RNF-20 |
| CA-06 | Dado um investidor com saldo, limite e mercado aberto, quando ele envia uma ordem de compra valida, entao a ordem eh criada, validada, enviada e o saldo correspondente eh reservado. | RF-05, RF-07, RN-07 |
| CA-07 | Dado um investidor sem saldo suficiente, quando ele envia uma ordem de compra, entao a ordem eh REJEITADA com o motivo "saldo insuficiente" e o investidor eh notificado. | RF-07, RF-15 |
| CA-08 | Dado um investidor sem a quantidade de ativos, quando ele envia uma ordem de venda, entao a ordem eh REJEITADA com o motivo "posicao insuficiente". | RF-08, RN-08 |
| CA-09 | Dada uma ordem acima do limite de risco do investidor, quando ela eh enviada, entao eh REJEITADA com o motivo "limite excedido". | RF-13 |
| CA-10 | Dado que o mercado esta fechado, quando o investidor envia uma ordem, entao ela eh REJEITADA com o motivo "mercado fechado". | RF-14, RN-10 |
| CA-11 | Dada uma ordem ENVIADA e ainda nao executada, quando o investidor a cancela, entao o status passa a CANCELADA, a reserva eh liberada e o investidor eh notificado. | RF-06, RN-12 |
| CA-12 | Dada uma ordem EXECUTADA, quando o investidor tenta cancela-la, entao o sistema nega o cancelamento. | RF-06, RN-06 |
| CA-13 | Dada uma ordem enviada, quando o investidor consulta o status, entao ve o status atual, e cada mudanca de status eh uma transicao valida. | RF-09, RN-06 |
| CA-14 | Dadas duas requisicoes com a mesma chave de idempotencia em ate 3600 segundos, quando ambas chegam ao sistema, entao apenas uma ordem eh criada. | RNF-09, RN-14 |
| CA-15 | Dada uma Bolsa que nao responde, quando o sistema envia uma ordem, entao tenta ate 3 vezes com intervalo de 1 segundo e, se todas falharem, a ordem passa a FALHA e o investidor eh notificado. | RNF-11, RNF-12, RN-15 |
| CA-16 | Dada a Bolsa indisponivel, quando o investidor tenta enviar uma nova ordem, entao ela nao eh aceita e ele recebe aviso claro, mantendo-se as consultas. | RNF-14, RN-16 |
| CA-17 | Dado um evento relevante, quando ele ocorre, entao existe um registro com data e hora, usuario, acao e resultado, que nao pode ser alterado nem apagado. | RF-11, RNF-17 |
| CA-18 | Dado um auditor autenticado, quando ele consulta os registros, entao consegue rastrear uma ordem do envio a conclusao; um administrador que tente o mesmo acesso eh negado. | RF-17, RN-19 |
| CA-19 | Dado um investidor autenticado, quando ele consulta o historico, entao ve todas as suas ordens com o status atual. | RF-16, RN-20 |
| CA-20 | Dada uma falha de servico, quando o sistema se recupera, entao retoma a operacao em ate 30 segundos sem perder ordens ja aceitas. | RNF-15, RNF-13 |