We have a backup management application UI hosted on Nautilus's backup server in Stratos DC. That backup management application code is deployed under Apache on the backup server itself, and Nginx is running as a reverse proxy on the same server. Apache and Nginx ports are 8083 and 8094, respectively. We have iptables firewall installed on this server. Make the appropriate changes to fulfill the requirements mentioned below:


We want to open all incoming connections to Nginx's port and block all incoming connections to Apache's port. Also make sure rules are permanent.

```sh
telnet
telnet stbkp01 8093
telnet stbkp01 8094

New Terminal
ssh clint@stbkp01
systemctl status iptables
iptables -L
iptables -A INPUT -p tcp --dport 8094 -m conntrack --ctstate NEW,ESTABLISHED -j ACCEPT
iptables -A INPUT -p tcp --dport 8083 -m conntrack --ctstate NEW -j REJECT
systemctl start iptables
systemctl status iptables
service iptables save
iptables -L
```
