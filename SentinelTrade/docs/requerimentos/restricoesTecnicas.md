# Restricoes Tecnicas

| ID | Restricao | Descricao |
|---|---|---|
| RT-01 | Linguagem | O sistema sera desenvolvido em Java 21. |
| RT-02 | Ferramenta de build | Maven ou Gradle (a decidir). |
| RT-03 | Dados simulados | A bolsa e o dinheiro, assim como os ativos e cotacoes sao simulados. |
| RT-04 | Arquitetura distribuida | O sistema deve ser uma plataforma distribuida, com provedor de cotacoes, Bolsa/Corretora e servico de notificacao como componentes externos acessados por interfaces. |
| RT-05 | Comunicacao segura | Toda comunicacao entre componentes e com usuarios deve usar TLS. |
| RT-06 | Configuracao externa | Parametros de ambiente, time-outs, retentativas e segredos devem vir de variaveis de ambiente (`.env`), nunca fixos no codigo. |
| RT-07 | Segredos fora do repositorio | Senhas, tokens e chaves de API nao podem ser versionados, o `.env` fica no `.gitignore` e o modelo em `.env.example`. |
| RT-08 | Processamento assincrono | O envio de ordens a Bolsa/Corretora deve usar fila de mensagens (tecnologia a decidir). |
| RT-09 | Banco de dados | Banco relacional com suporte a transacoes atomicas (a decidir). |
