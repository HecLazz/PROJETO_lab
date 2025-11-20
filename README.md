# 🔒 Projeto: Laboratório de Cibersegurança – Blue Team & Red Team

Este repositório documenta a construção de um laboratório completo de cibersegurança, criado com foco no aprendizado prático das áreas de **Blue Team**, **Red Team** e **Análise de Logs**.

O objetivo do projeto é estudar, implementar e simular cenários reais de segurança defensiva e ofensiva, utilizando ferramentas reconhecidas no mercado, como:

- **Wazuh (SIEM + XDR)**  
- **Metasploitable 3 (Ubuntu)**  
- **Máquinas virtuais para ataque e defesa**  
- **Ferramentas de pentest, automação e monitoramento**

## 🎯 Objetivos do Laboratório

- Criar um ambiente isolado que simule uma infraestrutura real.  
- Aprender na prática a instalar, configurar e integrar ferramentas de segurança.  
- Gerar, monitorar e analisar logs com Wazuh SIEM.  
- Testar vulnerabilidades, identificar alertas e compreender a resposta a incidentes.  
- Evoluir diariamente com documentação detalhada (presente em `EVOLUCAO.md`).  

## 🧩 Arquitetura Atual

- **Wazuh Manager + Dashboard** (CentOS)
- **Victim Machine – Metasploitable 3** (Ubuntu)
- **Attacker Machine** (Kali Linux)
- **rede interna isolada (`blue-team-net` `red-team-net`)**

## 📁 Documentação do Projeto

- **EVOLUCAO.md** → diário técnico com logs, configurações, problemas, soluções e avanços.
- **configs/** → arquivos de configuração criados durante o projeto.
- **scripts/** → scripts úteis para automação e testes.

Este laboratório está em constante atualização conforme avanço nos estudos e testes práticos em segurança ofensiva e defensiva.
