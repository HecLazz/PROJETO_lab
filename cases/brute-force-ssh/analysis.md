# Analysis

O Wazuh identificou múltiplas tentativas de autenticação falhas em um curto período de tempo,
caracterizando um ataque de brute force.

### Key indicators

- Repetidas falhas de autenticação SSH
- Mesmo endereço IP de origem
- Usuários inexistentes
- Escalada de severidade nos alertas

### MITRE ATT&CK Mapping

- T1110.001 – Password Guessing
- T1021.004 – Remote Services (SSH)

Nenhuma autenticação bem-sucedida foi identificada.

### New Analysis - After SSH Hardening

Após mudar a porta SSH e limitar MaxAuthTries, as tentativas de brute force atingiram o limite de autenticação em menos de um minuto.

Isso confirma que o MaxAuthTries reduz a superfice de ataque, mas não impede de ataques automáticos.

Após instalar e configurar o Fail2Ban, percebi que depois de 3 tentativas e erro, o IP foi bloqueado e ao tentar novamente acessar, o SSH retorna *connection refused*. Significa que o Fail2Ban está agindo como o esperado.
