System admins team of xFusionCorp Industries has setup some scripts on jump host that run on some regular intervals and perform some operations on all app servers in Stratos Datacenter. To make these scripts work properly we need to make sure thor user on jump host has password less SSH access to all app servers through their respective sudo users. So based on the requirements:


Setup a passwordless authentication for user thor on jump host to all app servers through their respective sudo users.

ssh-keygen -t rsa
cat /tmp/p
ssh-copy-id tony@stapp01
ssh-copy-id steve@stapp02
ssh-copy-id banner@stapp03
ssh tony@stapp01
ssh steve@stapp02
ssh banner@stapp03
