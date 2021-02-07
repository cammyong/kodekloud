For some security reasons xFusionCorp Industries security team has decided to use custom Apache users for each web application hosted there rather than its default user. Since this is going to be the Apache user so it shouldn't use the default home directory. Create the user as per requirements given below:


a. Create a user named anita on the App server 3 in Stratos Datacenter.

b. Set UID to 2055 and its home directory to /var/www/anita


ssh banner@stapp03
id anita
cat /etc/passwd |grep anita
useradd -u 2055 anita
cat /etc/passwd |grep anita
id anita
usermod -d /var/www/anita -m anita
cat /etc/passwd |grep anita
