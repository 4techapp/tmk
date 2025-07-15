# tmk
Base de Conhecimento TMK x Gcom x 4tech

  **Este repositÓrio visa a melhoria, boa prática e base de conhecimento, nos processos de migração, e produção do sistema Gcom , tendo como foco hardwares, aplicações e infra estrutura de rede .**

indrodução :
** Link Internet **
                        +--------------------+
                        |      INTERNET      |
                        +---------+----------+
                                  |
                        +---------v----------+
                        |     ROTEADOR       |
                        |  (com Failover)    |
                        +---------+----------+
                                  |
                       +----------+----------+
                       |                     |
                +------v-----+        +------v-----+
                |  LINK 1    |        |  LINK 2    |
                | PRINCIPAL  |        |  BACKUP    |
                +------------+        +------------+
                       ▲                     ▲
                       |                     |
          Teste de conexão (ping)     Ativado se falha
                 via LINK 1           no principal detectada
                       |
            +----------v-----------+
            | LINK 1 FUNCIONANDO?  |
            +----------+-----------+
                       |
          +------------+------------+
          |                         |
       [ SIM ]                  [ NÃO ]
          |                         |
  +-------v--------+      +--------v--------+
  | Usar LINK 1    |      | Ativar LINK 2   |
  | normalmente    |      | Desativar LINK 1|
  +----------------+      +-----------------+
                                 |
                 +---------------v----------------+
                 | Continuar monitorando LINK 1   |
                 +--------------------------------+

