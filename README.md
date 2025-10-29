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
