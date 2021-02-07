New tools have been installed on the app server in Stratos Datacenter. Some of these tools can only be managed from the graphical user interface. Therefore, there are requirements for these app servers.


On all App servers in Stratos Datacenter change the default runlevel so that they can boot in GUI (graphical user interface) by default.



ssh tony@stapp01
systemctl get-default
systemctl status graphical.target
systemctl start graphical.target
systemctl enable graphical.target
systemctl status graphical.target
systemctl get-default
systemctl set-default graphical.target
systemctl get-default

ssh steve@stapp02
systemctl get-default
systemctl status graphical.target
systemctl start graphical.target
systemctl enable graphical.target
systemctl status graphical.target
systemctl get-default
systemctl set-default graphical.target
systemctl get-default

ssh banner@stapp03
systemctl get-default
systemctl status graphical.target
systemctl start graphical.target
systemctl enable graphical.target
systemctl status graphical.target
systemctl get-default
systemctl set-default graphical.target
systemctl get-default

