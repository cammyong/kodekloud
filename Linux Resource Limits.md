On our Storage server in Stratos Datacenter we are having some issues where nfsuser user is holding hundred of processes which is degrading the performance of server. So we have a requirement to limit its maximum processes. Please set its maximum process limits as below:


a. soft limit = 80

b. hard_limit = 93


ssh natasha@ststor01
cat /etc/security/limits.conf |grep nproc | grep -v ^#
vi /etc/security/limits.conf
nfsuser soft nproc 80
nfsuser hard nproc 93
cat /etc/security/limits.conf |grep nproc | grep -v ^#
