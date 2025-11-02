# PROJETO_lab

**DAY - 1**

Meu intuito com esse projeto é montar um laboratório de estudo, teste e prática.

Eu pretendo iniciar com 3 máquinas, Kali Linux, Metasploitable e Ubuntu:
- `Kali Linux` - Máquina para o Pentesting.
  - 5GB RAM
	- 3 CPU
- `Metasploitable` - Máquina Vulnerável.
  - 1GB RAM
	- 1 CPU
- `Ubuntu Server` - Máquina que vai rodar o GrayLog.
  - 5GB RAM
	- 3 CPU
    
Dentro do Ubuntu vou utilizar o GrayLog para fazer a análise da máquina vulnerável.  
Com as máquinas instaladas e atualizadas vou começar o processo de definir cada uma, primeiro passo ver se cada máquina se enxerga. Para isso no próprio virtualbox, configurei uma placa de rede (rede interna) para cada escopo, red-team-net e blue-team-net.
- `red-team-net` - Kali e Metasploitable.
- `blue-team-net` - Ubuntu e Metasploitable.
  
Configurei IP's para cada escopo e máquina, exemplo:

- `kali eth0` - 10.10.10.10/24
- `metasploitable eth0` - 10.10.10.5/24  
- `ubuntu enp0s3` - 10.20.20.10/24
- `metasploitable eth1` - 10.20.20.5/24
---
**DAY - 2**

Começar a instalar e configurar o GrayLog na máquina com Ubuntu Server. Após algumas pesquisas cheguei a conclusão de fazer toda essa instalação através do Docker.

- Link do Graylog: https://github.com/lawrencesystems/graylog.git

Me deparei com um problema, o graylog estava rodando infinitamente e não iniciava nunca, percebi que o MongoDB agora exige AVX do processador por mais que meu computador tenha, o virtualbox parece não transmitir essa funcionalidade para as máquinas, mesmo eu habilitando o VT-x/AMD dentro do virtualbox.
A partir disso fui pesquisar outras ferramentas e me deparei com o Security Onion, então vou adaptar o laboratório para essa ferramenta.

Link do download https://github.com/Security-Onion-Solutions/securityonion/blob/2.4/main/DOWNLOAD_AND_VERIFY_ISO.md

Hoje praticamente foi só pesquisando qual seria a melhor ferramenta para o laboratório, e cheguei a conclusão de adaptar o Security Onion mesmo, ainda mais que tem o Suricata que é uma ferramenta interessantíssima por ser uma IDS, IPS e NSM, isso vai elevar meus estudos para um nível maior.

Apesar dos impasses e erros, acredito que dar um passo pra trás é importante para você conseguir ter uma noção maior e melhorar as ideias, e começar a pesquisar melhor analisando cada detalhe, torna suas ideias mais forte e melhores.

---

PROJETO — Laboratório 
**Day 3**

Hoje enfrentei um problema de hardware ao tentar rodar o Security Onion, então mudei de estratégia e adotei o Wazuh via OVA (sistema baseado em CentOS). Configurei a rede com duas placas: uma em modo bridge e outra na rede interna blue-team-net. Fiz o teste de conectividade entre o Wazuh e a máquina vulnerável (Metasploitable) — ping OK.

Avaliei também a opção de instalar o Wazuh em uma VM Ubuntu, mas, por ora, a OVA dedicada está atendendo bem. Uma coisa que me chamou atenção: o Wazuh é bastante customizável e permite integrações úteis (ex.: VirusTotal), o que abre muitas possibilidades para análises e automação.

Próximo passo: implantar o agente Wazuh no Metasploitable. Como o Metasploitable é um sistema legado, imagino que a instalação direta pode ter incompatibilidades — então minha abordagem será pesquisar alternativas (agent forwarder, logs via syslog, ou versão adaptada do agente) e documentar cada tentativa. Tudo vai para o repositório com prints, comandos e notas.

Se você já passou por isso ou tem dica sobre agentes em sistemas legados, compartilha comigo — toda sugestão é bem-vinda!
