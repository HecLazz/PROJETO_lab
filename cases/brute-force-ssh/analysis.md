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
