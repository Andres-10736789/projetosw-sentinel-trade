# Matriz de Rastreabilidade

implementacao e teste ainda nao foram implementadas

## Requisitos funcionais

| Requisito | Diagrama | Regra / Criterio | Implementacao (planejada) | Teste |
|---|---|---|---|---|
| RF-01 | UC-01 | RN-02, CA-01 | Modulo de Cadastro | Planejado |
| RF-02 | UC-02 | RN-03, CA-02, CA-03 | Modulo de Autenticacao | Planejado |
| RF-03 | UC-03 | CA-04 | Modulo de Carteira | Planejado |
| RF-04 | UC-04 | RN-01, CA-05 | Modulo de Cotacoes | Planejado |
| RF-05 | UC-05 | RN-04, CA-06 | Modulo de Ordens | Planejado |
| RF-06 | UC-06 | RN-12, CA-11, CA-12 | Modulo de Ordens | Planejado |
| RF-07 | UC-11 | RN-07, CA-07 | Modulo de Validacao | Planejado |
| RF-08 | UC-11 | RN-08, CA-08 | Modulo de Validacao | Planejado |
| RF-09 | UC-07 | RN-05, RN-06, CA-13 | Modulo de Ordens | Planejado |
| RF-10 | UC-12 | RN-17 | Modulo de Notificacao | Planejado |
| RF-11 | UC-13 | RN-18, CA-17 | Modulo de Auditoria | Planejado |
| RF-12 | UC-09 | RN-09 | Modulo de Limites | Planejado |
| RF-13 | UC-11 | RN-09, CA-09 | Modulo de Validacao | Planejado |
| RF-14 | UC-11 | RN-10, CA-10 | Modulo de Validacao | Planejado |
| RF-15 | UC-11 | RN-11 | Modulo de Validacao | Planejado |
| RF-16 | UC-08 | RN-20, CA-19 | Modulo de Ordens | Planejado |
| RF-17 | UC-10 | RN-19, CA-18 | Modulo de Auditoria | Planejado |

## Requisitos nao funcionais

| Requisito | Diagrama | Regra / Criterio | Implementacao (planejada) | Teste |
|---|---|---|---|---|
| RNF-01 | UC-02 | - | Modulo de Autenticacao (hash com salt) | Planejado |
| RNF-02 | UC-02 | RN-03, CA-03 | Modulo de Autenticacao | Planejado |
| RNF-03 | UC-02 | - | Modulo de Autenticacao (sessao) | Planejado |
| RNF-04 | Todos | RN-19, CA-04, CA-18 | Controle de acesso por perfil | Planejado |
| RNF-05 | Todos | - | TLS e criptografia em repouso | Planejado |
| RNF-06 | Todos | - | Camada de validacao de entradas | Planejado |
| RNF-07 | Todos | - | Camada de acesso a dados (consultas parametrizadas) | Planejado |
| RNF-08 | Todos | - | Tratador global de excecoes | Planejado |
| RNF-09 | UC-05 | RN-14, CA-14 | Modulo de Ordens (idempotencia) | Planejado |
| RNF-10 | Todos | RT-06, RT-07 | `.gitignore`, `.env.example` | Planejado |
| RNF-11 | UC-05 | RN-15, CA-15 | Adaptadores de integracao | Planejado |
| RNF-12 | UC-05 | RN-15, CA-15 | Adaptadores de integracao | Planejado |
| RNF-13 | UC-05 | RT-08, CA-20 | Fila de mensagens | Planejado |
| RNF-14 | UC-05 | RN-16, CA-16 | Modulo de Ordens e integracoes | Planejado |
| RNF-15 | Todos | CA-20 | Mecanismo de recuperacao | Planejado |
| RNF-16 | UC-05 | RN-07 | Camada de transacoes | Planejado |
| RNF-17 | UC-13 | RN-18, CA-17 | Modulo de Auditoria | Planejado |
| RNF-18 | Todos | RN-19 | Controle de acesso e auditoria | Planejado |
| RNF-19 | Todos | - | Infraestrutura e monitoramento | Planejado |
| RNF-20 | UC-04, UC-05 | RN-16, CA-05 | Modulo de Cotacoes e Ordens | Planejado |
| RNF-21 | Todos | - | Identificador unico de ordem; esta matriz | Planejado |
| RNF-22 | Todos | - | Estrutura modular com interfaces | Planejado |