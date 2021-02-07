There are specific access levels for users defined by the xFusionCorp Industries system admin team. Rather than providing access levels to every individual user, the team has decided to create groups with required access levels and add users to that groups as needed. See the following requirements:


a. Create a group named nautilus_admin_users in all App servers in Stratos Datacenter.

b. Add the user john to nautilus_admin_users in all App servers. (create the user if not present already)


ssh tony@stapp01
sudo su -
id john
cat /etc/passwd/ |grep john
groupadd nautilus_admin_users
useradd -G nautilus_admin_users john
cat /etc/passwd/ |grep john
id john

ssh steve@stapp02
sudo su -
id john
cat /etc/passwd/ |grep john
groupadd nautilus_admin_users
useradd -G nautilus_admin_users john
cat /etc/passwd/ |grep john
id john

ssh banner@stapp03
sudo su -
id john
cat /etc/passwd/ |grep john
groupadd nautilus_admin_users
useradd -G nautilus_admin_users john
cat /etc/passwd/ |grep john
id john
