For our infrastructure in Stratos Datacenter, we need to serve our website code from a common/shared location that can be shared among all app nodes. To solve this, we came up with a solution to use the NFS (Network File System) server where we can store the data and mount the share among our app nodes. The dedicated NFS server will be our storage server. To accomplish this task, perform the following steps:


Install required NFS packages on storage server.

Configure storage server to act as an NFS server.

Make a NFS share /opt on storage server.

Install and configure NFS client packages on all app nodes and configure them to act as NFS client.

Mount /opt directory on all app nodes at /var/www/data directory (Create the directories if don't exist).

Start and enable required services.

There is an /tmp/index.html file on jump host. Copy this file on NFS server (storage server) under /opt and make sure it gets replicated to all app servers in mounted location.

```sh
ssh natasha@ststor01
yum install nfs-utils nfs-utils-lib -y
vi /etc/exports
/opt 172.16.238.10(rw,sync,no_root_squash)
/opt 172.16.238.11(rw,sync,no_root_squash)
/opt 172.16.238.12(rw,sync,no_root_squash)

systemctl enable nfs-server && systemctl start nfs-server && systemctl status nfs-server
exportfs -av
showmount -e ststor01
yum install openssh-clients openssh
ll -lsd /opt/


thor@jump
sudo scp /tmp/index.html natasha@ststor01:/tmp
cat/tmp/p

Back to ststor01
mv /tmp/index.html /opt
ll /opt


webser1
ssh tony@stapp01
ll -lsd /var/www/data
mkdir -p /var/www/data
yum install nfs-utils nfs-utils-lib -y
systemctl enable nfs-server && systemctl start nfs-server && systemctl status nfs-server
mount -t nfs ststor01:/opt /var/www/data
df -h
ll /var/www/data/

#Do for the rest webapp
```
