# tmk
Base de Conhecimento TMK x Gcom x 4tech

  **Este repositÓrio visa a melhoria, boa prática e base de conhecimento, nos processos de migração, e produção do sistema Gcom , tendo como foco hardwares, aplicações e infra estrutura de rede .**

indrodução :
** Link Internet **
 - O fluxo abaixo explica de forma simples , como o Mikrotik irá tratar uma falha no link de internet.
   ## 🌐 Diagrama de Failover de 2 Links

| Etapa               | Ação                                                                 |
|---------------------|----------------------------------------------------------------------|
| Monitoramento       | Testar conectividade do LINK 1 (principal), ex: `ping 8.8.8.8`       |
| Verificação         | LINK 1 está respondendo?                                              |
| Se SIM              | Manter uso do LINK 1 (principal)                                     |
| Se NÃO              | Ativar LINK 2 (backup) e desativar LINK 1                            |
| Loop                | Continuar testando o LINK 1 periodicamente                           |
| Retorno do LINK 1   | Se voltar a funcionar, reativar LINK 1 e desativar LINK 2 (failback) |


 
