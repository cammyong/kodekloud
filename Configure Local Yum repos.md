Nautilus production support team and security team had a meeting last month in which they decided to use local yum repositories for maintaing packages needed for their servers. For now they have decided to configure a local yum repo on Nautilus Backup Server. This is one of the pending item from last month so please configure a local yum repository on Nautilus Backup Server as per details given below.


a. We have some packages already present at location /packages/downloaded_rpms/ on Nautilus Backup Server.

b. Create a yum repo named yum_local and make sure to set Repository ID to yum_local. Configure it to use packages location /packages/downloaded_rpms/.

c. Install package wget from this newly created repo.

ssh clint@stbkp01
sudo -i
yum repolist
ll /packages/downloaded_rpms/
cd /etc/yum.repos.d/
ll
vi  yum_local
[yum_local]
name=yum_local
baseurl=file:///packages/downloaded_rpms/
enabled = 1
gpgcheck = 0
ll
yum repolist
mv yum_local yum_local.repo
ll
yum repolist
yum install httpd
yum repolist


