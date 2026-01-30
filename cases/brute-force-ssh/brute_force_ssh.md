## Case – Brute Force SSH Detectado com Wazuh

**Contexto**

Este case foi desenvolvido em ambiente de laboratório, com o objetivo de praticar detecção, análise e resposta a incidentes (IR) utilizando o SIEM Wazuh.

**Detecção do Evento**

O Wazuh gerou alertas relacionados a falhas de autenticação SSH, indicando tentativas repetidas de acesso com usuário inexistente.

**Principais indicadores observados:**
- `data.srcuser`: usuário inexistente
- `data.srcip`: IP de origem único e recorrente
- `rule.groups`: sshd, authentication_failed, invalid_login

**Análise**

Ao correlacionar os eventos e analisar a linha do tempo, foi identificado um padrão claro de password guessing:

- 18:34 – 18:35	= 18 Tentativas
- 18:35 – 18:36	= 220 Tentativas
- 18:36 – 18:37	= 222 Tentativas

O volume crescente de tentativas em curto intervalo confirma o comportamento automatizado.

**Classificação do Incidente**

Com base nos critérios definidos no playbook de brute force SSH, o evento foi classificado como:

- **Tipo:** Brute Force SSH
- **MITRE ATT&CK:**
    - `T1110.001` – Password Guessing
    - `T1021.004` – SSH
- **Táticas:**
    - Credential Access
    - Lateral Movement

**Impacto**
- **Host afetado:** Sistema Linux monitorado pelo agente Wazuh
- **IP de origem:** Externo
- **Comprometimento:** ❌ Não houve login bem-sucedido
- **Severidade:** Média

**Resposta e Contenção**

De acordo com o playbook, as seguintes ações foram consideradas:
- Monitoramento contínuo do IP de origem
- Aplicação de rate-limit em tentativas SSH
- Bloqueio do IP em caso de recorrência

**Hardening Recomendado**

- Avaliar autenticação por chave SSH
- Restringir usuários permitidos no serviço SSH
- Reduzir exposição do serviço a ataques automatizados

**Lições Aprendidas**

- Eventos isolados não caracterizam incidentes
- Correlação temporal é essencial para identificação de brute force
- Playbooks auxiliam na padronização de decisões
- Hardening reduz a recorrência de ataques

**⚠️ Nota:** Este estudo foi realizado em ambiente de laboratório, sem utilização de dados reais ou ambientes produtivos.
