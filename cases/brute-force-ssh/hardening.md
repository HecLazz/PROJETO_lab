# SSH Hardening Applied

Após a detecção do ataque, foram aplicadas medidas de hardening no serviço SSH
com o objetivo de dificultar novas tentativas de exploração.

## Changes Applied

- Alteração da porta padrão do SSH (22 → 65002)
- Configuração do parâmetro MaxAuthTries para 3 tentativas
- Redução do tempo de autenticação (120s → 60s)
- Ajuste de firewall para permitir apenas a nova porta configurada
- Instalação e Configuração do Fail2Ban

## Validation

Após as alterações:

- O Nmap passou a identificar a porta 22 como *closed*
- Tentativas de brute force com Hydra falharam na porta padrão
- Bloqueio de IP com Fail2Ban, retornando *connection refused*
- O atacante precisaria identificar a nova porta antes de tentar qualquer exploração

Essas medidas não impedem ataques, mas aumentam significativamente o esforço do atacante,
reduzindo a superfície de ataque e melhorando a postura de segurança do sistema.

