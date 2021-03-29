The system admins team of xFusionCorp Industries needs to deploy a new application on App Server 2 in Stratos Datacenter. They have some pre-requites to get ready that server for application deployment. Prepare the server as per requirements shared below:


Install and configure nginx on App Server 2.

On App Server 2 there is a self signed SSL certificate and key present at location /tmp/nautilus.crt and /tmp/nautilus.key. Move them to some appropriate location and deploy the same in Nginx.

Create an index.html file with content Welcome! under Nginx document root.

For final testing try to access the App Server 2 link (either hostname or IP) from jump host using curl command. For example curl -Ik https://<app-server-ip>/.

```sh
ssh steve@stapp02
sudo su -
yum install nginx
yum install epel-release
yum install nginx
ll /tmp/
vi /etc/nginx/nginx.conf
servername 172.16.238.11;

#uncomment "Settings for a TLS enabled server " section and add the servername
# uncomment "Load configuration files for the default server block" section and remove # from include /etc/nginx/default.d/^.conf 


#change the self signed SSL certificate and key present at location to an appropriate location
ssl_certificate_key "/etc/pki/nginx/server.crt" to /etc/pki/CA/certs/nautilus.crt"
ssl_certificate_key "/etc/pki/nginx/server.crt" /etc/pki/CA/private/nautilus.key";


cp /tmp/nautilus.crt /etc/pki/CA/certs/
cp /tmp/nautilus.key /etc/pki/CA/private/

ll /etc/pki/CA/certs/

cat /etc/nginx/nginx.conf |grep root

ll -lsd /usr/share/nginx/html/index.html
rm /usr/share/nginx/html/index.html
vi /usr/share/nginx/html/index.html
Welcome!

cat /usr/share/nginx/html/index.html

systemctl start nginx
systemctl status nginx
curl -Ik https://stapp02

# new terminal for test
curl -Ik https://stapp02
```

