
#

1. Install cronie package on all Nautilus app servers and start crond service.

2. Add a cron */5* ** * echo hello > /tmp/cron_text for root user.

```sh
ssh tony@stapp01
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
```
