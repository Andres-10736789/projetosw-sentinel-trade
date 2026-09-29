# Requisitos

## Requisitos Funcionais

| ID | RF | Descricao |
|---|---|---|
| RF-01 | Cadastro de investidores | O sistema deve permitir o cadastro de novos investidores. |
| RF-02 | Autenticação com MFA | O Sistema deve exigir do investidor um segundo fator de verificao (MFA), alem de sua senha. |
| RF-03 | Consulta de carteira | O Sistema deve permitir que o investidor consulte o saldo e os ativos de sua carteira. |
| RF-04 | Consulta de cotações | O Sistema deve permitir que o investidor veja as cotacoes dos ativos negociaveis. |
| RF-05 | Envio de ordem de compra e venda | O Sistema deve permitir que o investidor envie ordens de compra e venda de ativos. |
| RF-06 | Cancelamento de ordem | O Sistema deve permitir que o investidor possa cancelar a sua ordem de venda ou compra que ainda nao foi executada. |
| RF-07 | Validação de saldo | O Sistema deve ser capaz de verificar o saldo do investidor para confirmar se uma compra possa ser realizada. |
| RF-08 | Validacao de posicao | O sistema deve verificar, antes de transmitir uma ordem de venda se o investidor possui em sua carteira a quantidade de ativos que deseja vender. |
| RF-09 | Acompanhamento do status da ordem | O Sistema deve permitir que o investidor acompanhe o status da ordem de compra ou venda requisitada por ele. | 
| RF-10 | Notificacoes | O sistema deve notificar o investidor quando uma ordem for executada, rejeitada, cancelada ou falhar. |
| RF-11 | Registro de auditoria | O sistema deve registrar cada evento relevante (login, criacao, envio, execucao, rejeicao e cancelamento de ordens, alteracao de limites), com data e hora, usuario e resultado. |
| RF-12 | Gestao de limites | O sistema deve permitir que o administrador defina e altere os limites financeiros e de risco de cada investidor. |
| RF-13 | Validacao de limite de risco | O sistema deve verificar, antes de transmitir uma ordem, se ela respeita o limite de risco do investidor. |
| RF-14 | Validacao da situacao do mercado | O sistema deve verificar, antes de transmitir uma ordem, se o mercado esta aberto para negociacao do ativo. |
| RF-15 | Rejeicao com motivo | O sistema deve rejeitar a ordem que falhar em qualquer validacao e informar ao investidor o motivo. |
| RF-16 | Consulta de historico | O sistema deve permitir que o investidor consulte o historico de suas operacoes. |
| RF-17 | Consulta de auditoria | O sistema deve permitir que o auditor consulte os registros de auditoria e rastreie as operacoes. |

## Requisitos Não Funcionais

## Segurança

| ID | RF | Descrição |
|---|---|---|
| RNF-01 | Proteção de senhas | O sistema deve armazenar senhas somente na forma de hash com salt, nunca em texto puro. |
| RNF-02 | Autenticação multifator | O código de verificação (MFA) deve ser válido por 30 segundos, e a conta deve ser bloqueada temporariamente após 5 tentativas consecutivas incorretas. |
| RNF-03 | Expiração de sessão | A sessão do usuário deve expirar após 30 minutos, exigindo nova autenticação. |
| RNF-04 | Controle de acesso por perfil | Cada perfil (Investidor, Administrador e Auditor) deve acessar somente as funções do seu papel, e o investidor deve acessar somente os próprios dados. |
| RNF-05 | Confidencialidade dos dados | Dados pessoais e financeiros devem ser protegidos com criptografia em trânsito (TLS) e em repouso, e não podem aparecer em logs nem em mensagens de erro. |
| RNF-06 | Validação de entradas | Toda entrada deve ser validada no servidor (tipo, formato, tamanho e faixa de valores) antes de ser processada. |
| RNF-07 | Prevenção de injeção | O sistema deve usar consultas parametrizadas, sem concatenar entradas do usuário em comandos ou consultas. |
| RNF-08 | Tratamento seguro de exceções | Erros devem exibir ao usuário apenas mensagens genéricas, sem detalhes internos, e os detalhes técnicos devem ser gravados somente em log. |
| RNF-09 | Proteção contra duplicidade de ordem | Ordens com a mesma chave de idempotência devem ser processadas uma única vez dentro de uma janela de 3600 segundos. |
| RNF-10 | Ausência de segredos no repositório | Nenhuma senha, token ou chave pode ser versionado; a configuração sensível deve vir de variáveis de ambiente, com o `.env` ignorado pelo Git. |

## Resiliência

| ID | RF | Descrição |
|---|---|---|
| RNF-11 | Time-out de integração | Chamadas ao provedor de cotações, à Bolsa/Corretora e ao serviço de notificação devem ser interrompidas após 1 segundo sem resposta. |
| RNF-12 | Retentativa controlada | Após uma falha de integração, o sistema deve tentar novamente até 3 vezes, com intervalo de 1 segundo; esgotadas as tentativas, a falha deve ser registrada e o investidor notificado. |
| RNF-13 | Processamento assíncrono | O envio de ordens à Bolsa/Corretora deve ocorrer por fila de mensagens, de modo que nenhuma ordem aceita seja perdida se a Bolsa estiver indisponível. |
| RNF-14 | Indisponibilidade segura | Com a Bolsa ou o provedor de cotações indisponíveis, o sistema deve impedir o envio de novas ordens com aviso claro ao investidor, sem usar cotações desatualizadas, mantendo as consultas disponíveis. |
| RNF-15 | Recuperação de falhas | Após uma falha, o sistema deve retomar a operação em até 30 segundos, sem perder ordens já aceitas. |
| RNF-16 | Consistência de dados | A atualização de saldo e posição deve ocorrer de forma atômica junto com a mudança de status da ordem, sem deixar estados parciais. |

## Qualidade

| ID | RF | Descrição |
|---|---|---|
| RNF-17 | Auditabilidade | Os logs de auditoria devem ser imutáveis, registrar data e hora, usuário, ação e resultado, e ser mantidos por no mínimo 5 anos. |
| RNF-18 | Integridade | Saldos, posições e ordens só podem ser alterados por operações autorizadas e registradas em auditoria. |
| RNF-19 | Disponibilidade | O sistema deve ter disponibilidade mínima de 99,9% ao mês. |
| RNF-20 | Desempenho | O sistema deve confirmar o recebimento de uma ordem em até 2 segundos em 95% das requisições, e as cotações exibidas não podem ter mais de 5 segundos de atraso. |
| RNF-21 | Rastreabilidade | Cada ordem deve ter um identificador único acompanhável do envio à conclusão, e cada requisito deve estar ligado a caso de uso, implementação e teste na matriz de rastreabilidade. |
| RNF-22 | Manutenibilidade | O código deve ser modular, com as integrações externas isoladas por interfaces, e os testes automatizados devem cobrir ao menos 70% das regras de negócio. |