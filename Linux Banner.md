During the monthly compliance meeting, it was pointed out that several servers in the Stratos DC do not have a valid banner. The security team has provided serveral approved templates which should be applied to the servers to maintain compliance. These will be displayed to the user upon a successful login.


Update the message of the day on all application and db servers for Nautilus. Make use of the approved template located at /tmp/nautilus_banner on jump host

ll -lsd /tmp/nautilus_banner
scp -r /home/thor/nautilus_banner tony@stapp01:/tmp
ssh -t tony@stapp01 'sudo mv /tmp/nautilus_banner /etc/motd'

scp -r /home/thor/nautilus_banner steve@stapp02:/tmp
ssh -t steve@stapp02 'sudo mv /tmp/nautilus_banner /etc/motd'


scp -r /home/thor/nautilus_banner banner@stapp03:/tmp
ssh -t banner@stapp03 'sudo mv /tmp/nautilus_banner /etc/motd'



scp -r /home/thor/nautilus_banner peter@stdb01:/tmp
ssh peter@stdb01
yum install openssh-clients
scp -r /home/thor/nautilus_banner peter@stdb01:/tmp
ssh -t tony@stapp01 'sudo mv /tmp/nautilus_banner /etc/motd'
ssh peter@stdb01

scp -r /home/thor/nautilus_banner peter@stdb01:/tmp
ssh -t peter@stdb01 'sudo mv /tmp/nautilus_banner /etc/motd'

ssh tony@stapp01
ssh steve@stapp02
ssh banner@stapp03
ssh peter@stdb01
