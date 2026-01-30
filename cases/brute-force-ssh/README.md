# Brute Force SSH – Detection, Analysis and Hardening

Este case documenta a simulação de um ataque de brute force via SSH em um laboratório próprio,
a detecção do ataque com Wazuh e as medidas de hardening aplicadas para reduzir a superfície de ataque.

## Environment

- Attacker: Kali Linux
- Target: Metasploitable 3 (Ubuntu)
- Monitoring: Wazuh Manager
- Network: Segmented (Red Team / Blue Team)

## Attack Simulation

O ataque foi simulado utilizando a ferramenta Hydra para brute force em serviço SSH.
Inicialmente, o serviço estava configurado com parâmetros padrão.

Ferramentas utilizadas:
- Hydra
- Nmap
- Wazuh
