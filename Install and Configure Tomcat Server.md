The Nautilus application development team recently finished the beta version of one of their Java-based applications, which they are planning to deploy on one of the app servers in Stratos DC. After an internal team meeting, they have decided to use the tomcat application server. Based on the requirements mentioned below complete the task:


a. Install tomcat server on App Server 1 using yum.

b. Configure it to run on port 5002.

c. There is a ROOT.war file on Jump host at location /tmp. Deploy it on this tomcat server and make sure the webpage works directly on base URL i.e without specifying any sub-directory anything like this http://URL/ROOT .

d. You can access the website on LBR link. To do so click on the + button on top of your terminal, select option Select port to view on Host 1, and after adding port 80 click on Display Port.

```sh
ssh banner@stapp03
sudo su -
yum install tomcat -y
cat /usr/share/tomcat/conf/server.xml |grep port
vi /usr/share/tomcat/conf/server.xml
......#connector port = 8000....6000
connector executor



stapp03
cat /usr/share/tomcat/conf/server.xml
scp /tmp/ROOT.war banner@stapp03:/tmp
cp /tmp/ROOT.war /usr/share/tomcat/webapps/
ll /usr/share/tomcat/webapps/
systemctl status tomcat
systemctl start tomcat
systemctl status tomcat

curl -i 172.16.238.12:5002
```
