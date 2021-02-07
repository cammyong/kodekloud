As per details shared by development team the new application release has some dependencies on back end. There are some packages/services need to be installed on all app servers under Stratos Datacenter. As per requirements please perform below given steps:


a. Install cups package on all the application servers.

b. Once installed, make sure it is enabled to start during boot.


ssh tony@stapp01
sudo yum install cups -y
sudo systemctl status cups
sudo systemctl start cups
sudo systemctl enable cups
sudo systemctl status cups
   
   ssh steve@stapp02
   sudo yum install cups -y
   sudo systemctl status cups
   sudo systemctl start cups
   sudo systemctl enable cups
   sudo systemctl status cups

   ssh banner@stapp03
   sudo yum install cups -y
   sudo systemctl status cups
   sudo systemctl start cups
   sudo systemctl enable cups
   sudo systemctl status cups
