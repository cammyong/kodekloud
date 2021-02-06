System admins team of xFusionCorp Industries has installed a backup agent tool on all app servers, as per tool's requirements they need to create a user with a non-interactive shell.Therefore, create a user named jim with a non-interactive shell in the app03 server.



    1  ssh to app server 03
    2  id jim
    3  cat /etc/passwd
    4  sudo adduser jim -s /sbin/nologin
    5  id jim
    6  cat /etc/passwd |grep jim
	
