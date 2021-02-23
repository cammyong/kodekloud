xFusionCorp Industries has hosted some static websites on Nautilus Application Servers in Stratos DC. There are some confidential directories on document root that need to be password protected. Since they are using Apache for hosting the websites so production support team has decided to use .htaccess with basic auth. There is a website needs to be uploaded to /var/www/html/finance on Nautilus App Server 2. But before that we need to setup the authentication.


1.Create /var/www/html/finance direcotry if doesn't exist.

2.Add an user savi in htpasswd and set its password to B4zNgHA7Ya.

3.There is a file /tmp/index.html placed on Jump Server. Copy the same to new directory you created, please make sure default document root should remain /var/www/html.



ll /tmp/index.html
scp /tmp/index.html banner@stapp02:/tmp


ssh steve@stapp02
sudo -i
systemctl status httpd
mkdir /var/www/html/finance
htpasswd -c /etc/httpd/.htpasswd siva
#paste the password from the question

vi /var/www/html/finance/.htaccess

AuthType Basic

AuthName "Password Required"

Require valid-user

AuthUserFile /etc/httpd/.htpasswd


mv /tmp/index.html /var/www/html/finance
systemctl start httpd
systemctl status httpd


curl -u siva http://stapp02:8080/financexFusionCorp Industries has hosted some static websites on Nautilus Application Servers in Stratos DC. There are some confidential directories on document root that need to be password protected. Since they are using Apache for hosting the websites so production support team has decided to use .htaccess with basic auth. There is a website needs to be uploaded to /var/www/html/finance on Nautilus App Server 2. But before that we need to setup the authentication.


1.Create /var/www/html/finance direcotry if doesn't exist.

2.Add an user savi in htpasswd and set its password to B4zNgHA7Ya.

3.There is a file /tmp/index.html placed on Jump Server. Copy the same to new directory you created, please make sure default document root should remain /var/www/html.



ll /tmp/index.html
scp /tmp/index.html banner@stapp02:/tmp


ssh steve@stapp02
sudo -i
systemctl status httpd
mkdir /var/www/html/finance
htpasswd -c /etc/httpd/.htpasswd siva
#paste the password from the question

vi /var/www/html/finance/.htaccess

AuthType Basic

AuthName "Password Required"

Require valid-user

AuthUserFile /etc/httpd/.htpasswd


mv /tmp/index.html /var/www/html/finance
systemctl start httpd
systemctl status httpd


curl -u siva http://stapp02:8080/finance
