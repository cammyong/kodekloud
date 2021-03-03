Nautilus system admins team has prepared some scripts to automate few day to day tasks. They want them to be deployed on all app servers in Stratos DC and need to set some scheduled run for all of them. Before that they need to test similar functionality with a sample cron job. So perform the steps given below:


1. Install cronie package on all Nautilus app servers and start crond service.

2. Add a cron */5 * * * * echo hello > /tmp/cron_text for root user.



```shssh tony@stapp01
yum install cronie```
`systemctl start crond.service`
`systemctl status crond.service`
crontab -u root -l
crontab -e
*/5 * * * * echo hello > /tmp/cron_text
crontab -u root -l
watch -n 5 ll /tmp
watch -n 5 ls -l /tmp
ll /tmp/

ssh steve@stapp02
yum install cronie 
systemctl start crond.service
systemctl status crond.service
crontab -u root -l
crontab -e
*/5 * * * * echo hello > /tmp/cron_text
crontab -u root -l
watch -n 5 ll /tmp
watch -n 5 ls -l /tmp
ll /tmp/

ssh banner@stapp03
yum install cronie 
systemctl start crond.service
systemctl status crond.service
crontab -u root -l
crontab -e
*/5 * * * * echo hello > /tmp/cron_text
crontab -u root -l
watch -n 5 ll /tmp
watch -n 5 ls -l /tmp
ll /tmp/

