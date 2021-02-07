xFusionCorp Industries security team recently did a security audit of their infrastructure and they came up with some ideas to improve the application/servers security. They decided to use SElinux for an additional security layer. They are still planning how they will actually go with it however they have decided to start testing with app servers so based on the recommendations they have below given requirements:


Install the required packages of SElinux on App server 2 in Stratos Datacenter and disable it permanently for now, it will be enabled after making some required configuration changes on this host. For now don't worry about rebooting the server since there is already a scheduled reboot tonight in maintenance window. Also ignore the status of SElinux whatever it shows from command line right now but the final status after reboot should be disabled.


ssh steve@stapp02
yum install selinux*
sestatus
cat /etc/selinux/config |grep SELINUX
vi /etc/selinux/config
# change SELINUX="enforcing" to "disabled"
cat /etc/selinux/config |grep SELINUX
sestatus

