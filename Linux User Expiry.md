A developer John has been assigned Nautilus project temporarily as a backup resource. Being a temporary resource for this project we need a temporary user for John. Its a good idea to create a user with some auto expiry date so that user won't be able to access servers once expired.


So create a user named john on the App server 3. Set expiry date to 2021-04-21 in Stratos Datacenter. Make sure the user is created as per standard and is in lowercase.

ssh -t banner@stapp03 'sudo chage -l john'
ssh -t banner@stapp03 'sudo chage -E 2021-04-21 john'
ssh -t banner@stapp03 'sudo chage -l john'
