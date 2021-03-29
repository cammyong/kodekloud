To secure our Nautilus infrastructure in Stratos Datacenter we have decided to install and configure firewalld on all app servers. We have Apache and Nginx services running on these apps. Nginx is running as a reverse proxy server for Apache. We might have more robust firewall settings in the future, but for now we have decided to go with the given requirements listed below:


a. Allow all incoming connections on Nginx port.

b. Allow incoming connections from LB host only on Apache port and block for all others.

c. All rules must be permanent.

d. Zone should be public.

e. If Apache or Nginx services aren't running already, please make sure to start them.


```sh
ssh tony@stapp01
systemctl status nginx && systemctl status httpd
grep -i Listen /etc/httpd/conf/ht* /etc/nginx/nginx.conf
yum install firewalld -y
systemctl start firewalld && systemctl enable firewalld && systemctl status firewalld
firewall-cmd --zone=public --add-port=8097/tcp --permanent
firewall-cmd --permanent --zone=public --add-service={http,https}
firewall-cmd --permanent --zone=public --add-rich-rule='rule family="ipv4" source address="172.16.238.14" port port=8089 protocol=tcp accept'

systemctl enable nginx && systemctl status nginx
systemctl enable httpd && systemctl status httpd
firewall-cmd --reload && systemctl restart firewalld && firewall-cmd --zone=public --list-all
curl localhost
curl localhost:8089

# Do same for the rest of the app servers.
```
