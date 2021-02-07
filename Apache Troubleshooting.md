xFusionCorp Industries utilizes monitoring tools to check the status of every service, application, etc. running on the systems. The monitoring system identified that Apache service is not running on some of the Nautilus Application Servers in Stratos Datacenter.


1.Identify the faulty Nautilus Application Servers and fix the issue. Also, make sure Apache service is up and running on all Nautilus Application Servers. Do not try to stop any kind of firewall that is already running.

2.Apache is running on 6100 port on all Nautilus Application Servers and its document root must be /var/www/html on all app servers.

3.Finally you can test from jump host using curl command to access Apache on all app servers and it should work fine. E.g. curl http://172.16.238.10:6100/


ssh tony@stapp01
systemctl status httpd
systemctl start httpd
systemctl status httpd
vi /etc/httpd/conf/httpd.conf


# error on stapp01
# change "Listen 8080" to Listen 172.16.238.10:6100
# change  DocumentRoot /var/www/html; to DocumentRoot /var/www/html

systemctl start httpd
curl http://172.16.238.10:6100

# error on stapp02
# change ServerRoot "/etc/httpd;" to ServerRoot /etc/httpd
systemctl start httpd
curl http://172.16.238.11:6100 
