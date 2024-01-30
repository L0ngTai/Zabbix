# Install Zabbix Agent for Rocky Linux
- excludepkgs=zabbix*
- rpm -Uvh https://repo.zabbix.com/zabbix/6.4/rhel/9/x86_64/zabbix-release-6.4-1.el9.noarch.rpm
- dnf install -y zabbix-agent
- vi /etc/zabbix/zabbix_agentd.conf
  + Server=IP Zabbix Proxy,IP local
  + ServerActive=IP Zabbix Proxy,IP local
  + Hostname=Name server
- firewall-cmd --zone=public --add-port=10050/tcp --permanent
- firewall-cmd --zone=public --add-port=10051/tcp --permanent
- firewall-cmd --reload
- systemctl start zabbix-agent
- systemctl enable zabbix-agent
- systemctl status zabbix-agent
  
# Install Zabbix Agent for Centos 7.9
- sudo rpm -Uvh https://repo.zabbix.com/zabbix/6.4/rhel/7/x86_64/zabbix-release-6.4-1.el7.noarch.rpm
- sudo yum install zabbix-agent -y
- sudo nano /etc/zabbix/zabbix_agentd.conf
  + Server=IP Zabbix Proxy,IP local
  + ServerActive=IP Zabbix Proxy,IP local
  + Hostname=Name server
- firewall-cmd --zone=public --add-port=10050/tcp --permanent
- firewall-cmd --zone=public --add-port=10051/tcp --permanent
- firewall-cmd --reload
- systemctl start zabbix-agent
- systemctl enable zabbix-agent
- systemctl status zabbix-agent

# Install Zabbix Agent for Ubuntu 22.04
- wget https://repo.zabbix.com/zabbix/6.4/ubuntu/pool/main/z/zabbix-release/zabbix-release_6.4-1+ubuntu22.04_all.deb
- dpkg -i zabbix-release_6.4-1+ubuntu22.04_all.deb
- apt install zabbix-agent
- sudo nano /etc/zabbix/zabbix_agentd.conf
  + Server=IP Zabbix Proxy,IP local
  + ServerActive=IP Zabbix Proxy,IP local
  + Hostname=Name server
- firewall-cmd --zone=public --add-port=10050/tcp --permanent
- firewall-cmd --zone=public --add-port=10051/tcp --permanent
- firewall-cmd --reload
- systemctl start zabbix-agent
- systemctl enable zabbix-agent
- systemctl status zabbix-agent
