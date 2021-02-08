Nautilus system admins team just deployed a web UI application for their backup utility running on Nautilus backup server in Stratos Datacenter. The application is running on port 8087 . They have firewalld installed on that server. Some requirements have came up as mentioned below:

Open all incoming connection on 8087/tcp port. Zone should be public. 

ssh clint@stbkp01
sudo su -
systemctl status firewalld
firewall-cmd --list-all --zone=public
firewall-cmd --permanent --zone=public --add-port=8087/tcp
firewall-cmd --reload
systemctl status firewalld
systemctl restart firewalld
systemctl status firewalld
firewall-cmd --zone=public --list-ports
