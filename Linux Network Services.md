Our monitoring tool has reported an issue in Stratos Datacenter. One of our app servers has an issue, as its Apache service is not reachable on port 3000 (which is our Apache port). The service itself could be down, the firewall could be at fault, or something else could be causing the issue.


Use tools like telnet, netstat, etc. to find and fix the issue. Also make sure Apache is reachable from the jump host without compromising any security settings.

```sh
telnet  stapp01 3000
telnet  stapp02 3000
telnet  stapp03 3000
quit

ssh tony@stapp01
systemctl status httpd
systemctl start httpd
systemctl status httpd
netsat -tulnp
ps -ef  |grep 257
kill 257
ps -ef  |grep 257
netsat -tulnp
systemctl start httpd && systemctl status httpd

#Back to jump server, telnet sappserver port number
telnet stapp01 3000


#Back to webserver1
netsat -tulnp
httpd -t
vi /etc/httpd/conf/httpd.conf
#Add Servername 172.16.238.10:3000
systemctl restart httpd
httpd -t
systemctl status httpd

#Back to jump server, telnet sappserver port number
telnet stapp01 3000


#Back to webserver1
netsat -tulnp
iptables -L
iptables -F

#Back to jump server, telnet sappserver port number
telnet stapp01 3000

```

