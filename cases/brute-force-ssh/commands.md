### Ubuntu-server (Vulnerável)
`sudo nano /etc/netplan/50-cloud-init.yaml` - arquivo de configuração do IP

`sudo netplan apply` - aplicar configurações do IP

`sudo fail2ban-client banned` - verificar IP bloqueado pelo fail2ban

`sudo nano /var/ossec/etc/ossec.conf` - arquivo de configuração do agent Wazuh

`sudo /var/ossec/bin/wazuh-control info` - verificar versão do agent

`sudo tail -f /var/log/auth.log` - acompanhar os logs

`sudo nano /etc/ssh/sshd_config` - arquivo de configuração do ssh

`sudo nano /etc/pam.d/sshd` - arquivo de configuração do PAM ssh

`sudo nano /etc/pam.d/common-auth` - arquivo de configuração de autenticação PAM

`sudo nano /home/ubuntu-user/.ssh/authorized_keys` - lista de chaves permitidas pelo ssh

`sudo ufw limit from 10.10.10.10 to any port 65002 proto tcp` - configuração do firewall (permitir o IP mas com rate-limit)

`sudo ufw allow from 10.20.20.11 to any port 65002 proto tcp` - configuração do firewall (permitir acesso)

`sudo ufw numbered` - numerar as configurações aplicadas ao firewall

`sudo ufw status` - status das configurações aplicadas ao firewall

### Kali Linux (Atacante)
`nmap -sS -sV 10.10.10.6 -p 65002` - -sS uma verificação mais discreta -sV para saber a versão e analisar justamente a porta SSH

`hydra -l FAKE -P /usr/share/wordlist/rockyou.txt 10.10.10.6 -t 4 ssh -s 65002` - Brute Force

`ssh ubuntu-user@10.10.10.6 -p 65002` - Testar a conexão com o SSH a cada configuração feita na máquina vulnerável.

**🚩 Todos os códigos e teste são para fins educativos.**
