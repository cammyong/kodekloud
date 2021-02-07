There is a critical issue going on with the Nautilus application in Stratos DC. The production support team identified that the application is unable to connect to the database. After digging into the issue, the team found that mariadb service is down on the database server.


Look into the issue and fix the same.


ssh peter@stdb01
sudo su -
systemctl status mariadb
systemctl start mariadb
systemctl status mariadb
ll /var/lib/mysql
systemctl start mariadb
chown mysql:mysql /var/run/mariadb
ll -lsd /var/run/mariadb
systemctl status mariadb
yum install mysql 
systemctl start mariadb
systemctl status mariadb
