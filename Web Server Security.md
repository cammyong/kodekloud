During a recent security audit, the application security team of xFusionCorp Industries found security issues with the Apache web server on Nautilus App Server 3 server in Stratos DC. They have listed several security issues that need to be fixed on this server. Please apply the security settings below:


a. On Nautilus App Server 3 it was identified that the Apache web server is exposing the version number. Ensure this server has the appropriate settings to hide the version number of the Apache web server.

b. There is a website hosted under /var/www/html/news on App Server 3. It was detected that the directory /news lists all of its contents while browsing the URL. Disable the directory browser listing in Apache config.

c. Also make sure to restart the Apache service after making the changes.


ssh banner@stapp03
systemctl status httpd
cat /etc/httpd/conf/httpd.conf |grep -i token
vi /etc/httpd/conf/httpd.conf


# Add ServerSignature and ServerTokens into IncludeOtional conf.d/*.conf section
ServerSignature Off
ServerTokens Prod

#remove Indexes under Options Indexes FollowSymLinks

cat /etc/httpd/conf/httpd.conf |grep -i token
cat /etc/httpd/conf/httpd.conf |grep -i sign
systemctl start httpd
systemctl status httpd

curl -I http://stapp03:8080
curl -I http://stapp03:8080/news
curl http://stapp03:8080/news
curl http://stapp03:8080/
cat /var/www/html/news/news.txt
curl http://stapp03:8080/news
