The production support team of xFusionCorp Industries has deployed some of the latest monitoring tools to keep an eye on every service, application, etc. running on the systems. One of the monitoring systems reported about Apache service unavailability on one of the app servers in Stratos DC.


Identify the faulty app host and fix the issue. Make sure Apache service is up and running on all app hosts. They might not hosted any code yet on these servers so you need not to worry about if Apache isn't serving any pages or not, just make sure service is up and running. Also, do not try to change the Apache port on any host.

```sh
ssh tony@stapp01
systemctl status httpd
systemctl start httpd
systemctl status httpd
netstat -tulnp
cat /etc/httpd/conf
cat /etc/httpd/conf/httpd.conf |grep Listen
netstat -tulnp
ps -ef |grep 261
kill -9 261
ps -ef |grep 261
netstat -tulnp
systemctl start httpd
systemctl status httpd



# check other servers 
```


