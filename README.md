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
