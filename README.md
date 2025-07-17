# TMK
Base de Conhecimento TMK x Gcom x 4tech

  **Este repositorio visa a melhoria, boa prática e base de conhecimento, nos processos de migração, e produção do sistema Gcom , tendo como foco hardwares, aplicações e infra estrutura de rede .**

# Link Internet
- Por padrão todas as unidades TEMAKERIA, utilizarão mesma estrutura de equipanetos, configurações e serviços descristos abaixo :

## Diagrama de Rede – Visão Geral

### Fluxo de Conexão com Failover

| Etapa                        | Descrição                                                                 |
|-----------------------------|---------------------------------------------------------------------------|
| 1. Conexão à Internet        | Dois links disponíveis: LINK1 (principal) e LINK2 (backup)                |
| 2. Roteador MikroTik         | Gerencia os dois links com mecanismo de failover                         |
| 3. Failover Ativo           | Se o LINK1 falhar, o MikroTik ativa automaticamente o LINK2              |
| 4. Rede Cabeada Interna      | Após o roteamento, o tráfego segue para a rede cabeada                   |
| 5. Dispositivos na LAN       | Conectados via cabo ou via UNIFI (Wi-Fi)                                 |
| 6. UNIFI Wi-Fi               | Fornece acesso a tablets e dispositivos móveis                           |
| 7. Computadores e Impressoras| Conectados via rede cabeada                                              |
| 8. Servidor Virtualizado     | Máquina física com VMs, incluindo o servidor do sistema GCOM             |
| 9. Banco de Dados SQL        | Hospedado dentro da VM do GCOM                                           |

---

### Estrutura de Rede Hierárquica

- INTERNET  
  - LINK1  
  - LINK2  
    - MIKROTIK  
      - FAIL_OVER  
      - REDE_CABEADA  
        - DISPOSITIVOS  
          - UNIFI  
            - TABLET  
            - DISPOSITIVOS MÓVEIS  
          - COMPUTADORES  
          - IMPRESSORAS  
          - SERVIDOR DE MÁQUINA VIRTUAL  
            - SERVIDOR VIRTUAL GCOM  
              - BANCO DE DADOS SQL




# Sobre o Mikrotik
- Equipamento encarregado em receber e tratar os links de internet, criar e gerir a rede interna , assim como todas as suas depenências, provendo dados, ferramentas, logs e recursos avançados. Sendo ele parte central do ecosistema . 
 

 
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

## Composição de equipamentos, cabemanto e perifericos utilizados. 

Rack de Red][click +detalhes](https://github.com/4techapp/tmk/blob/main/Rack)
Roteadores [click +detalhes](https://github.com/4techapp/tmk/blob/main/Routers)
Cabeamento [click +detalhes](https://github.com/4techapp/tmk/blob/main/cabeamento)
Aps Sem Fio [click +detalhes](https://github.com/4techapp/tmk/blob/main/wireless)
Servidor [click +detalhes](https://github.com/4techapp/tmk/blob/main/Servidor)
Servidor Virtual [click +detalhes](https://github.com/4techapp/tmk/blob/main/Servidor)
               
