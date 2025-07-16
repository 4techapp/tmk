# tmk
Base de Conhecimento TMK x Gcom x 4tech

  **Este repositorio visa a melhoria, boa prática e base de conhecimento, nos processos de migração, e produção do sistema Gcom , tendo como foco hardwares, aplicações e infra estrutura de rede .**

# indrodução :

# Link Internet
 Por padrão todas as unidades TEMAKERIA, utilizarão como padrão a estrutura de equipanetos, configurações e serviços descristos abaixo :

 INTERNET
    LINK1
    LINK2
        MIKROTIK
            FAIL_OVER
            REDE_CABEADA
                DISPOSITVOS
                    UNIFI
                        TABLET, DISPOSITIVOS MOVEIS
                    COMPUTADORES
                    IMPRESSORAS
                    SERVIDOR_DE_MAQUINA_VIRTUAL
                        SERVIDOR_VIRTUAL_GCOM
                            BANCO_DE_DADOS_SQL


 
 - O fluxo abaixo explica de forma simples , como o Mikrotik irá tratar uma falha no link de internet.
   ## Failover Mikrotik de 2 Links ##

| Etapa               | Ação                                                                 |
|---------------------|----------------------------------------------------------------------|
| Monitoramento       | Testar conectividade do LINK 1 (principal), ex: `ping 8.8.8.8`       |
| Verificação         | LINK 1 está respondendo?                                              |
| Se SIM              | Manter uso do LINK 1 (principal)                                     |
| Se NÃO              | Ativar LINK 2 (backup) e desativar LINK 1                            |
| Loop                | Continuar testando o LINK 1 periodicamente                           |
| Retorno do LINK 1   | Se voltar a funcionar, reativar LINK 1 e desativar LINK 2 (failback) |


 
