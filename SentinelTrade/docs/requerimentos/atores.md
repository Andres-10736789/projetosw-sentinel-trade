# Atores

| Ator | Tipo | Pessoa ou Sistema | Objetivo |
|---|---|---|---|
| Investidor | Primario | Pessoa | Consultar cotações e carteira, enviar e cancelar ordens de compra e venda, acompanhar o status das ordens e consultar o histórico de operações |
| Administrador | Primario | Pessoa | Cadastrar e gerenciar investidores, contas, e limites financeiros e de risco |
| Auditor | Primario | Pessoa | Consultar os registros de auditoria e rastrear operacoes |
| Provedor de cotacoes | Secundario | Sistema | Fornecer cotacoes ao SentinelTrade |
| Bolsa/Corretora | Secundario | Sistema | Receber ordens e devolver o resultado (execucao, rejeicao, cancelamento) |
| Servico de notificacao | Secundario | Sistema | Entregar ao investidor os avisos de execucao, rejeicao, cancelamento e falha |