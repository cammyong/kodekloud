The system admins team of xFusionCorp Industries has set up a new tool on all app servers, as they have a requirement to create a service user account that will be used by that tool. They are finished with all apps except for App 3 in Stratos Datacenter.

Create a user named javed in App Server 3 without a home directory.

ssh banner@stapp03
sudo su -
id javed
cat /etc/passwd |grep javed
useradd -M javed 
id javed
cat /etc/passwd |grep javed
