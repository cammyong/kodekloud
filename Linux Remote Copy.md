One of the Nautilus developers has copied confidential data on the jump host in Stratos DC. That data must be copied to one of the app servers. Because developers do not have access to app servers, they asked the system admins team to accomplish the task for them.

Copy /tmp/nautilus.txt.gpg file from jump server to App Server 2 at location /home/webdata


ll /tmp/nautilus.txt.gpg
sudo scp /tmp/nautilus.txt.gpg steve@stapp02:/tmp
ssh steve@stapp02
ll /tmp/
sudo mv /tmp/nautilus.txt.gpg /home/webdata
ll /home/webdata
