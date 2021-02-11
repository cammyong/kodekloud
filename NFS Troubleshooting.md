Nautilus production support team was trying to fix some issues with their storage server. Storage server has a shared directory /nfsshare which is mounted on all app servers at location /var/www/html so that whatever data they store on storage server under /nfsshare can be shared among all app servers. Now somehow NFS server is broken and having some issues.

Identify the root cause of issue and fix the same to make sure sharing works fine among all app servers and storage server.



ssh natasha@ststor01
systemctl status nfs-server && systemctl status rpcbind
cat /etc/exports
vi /etc/exports
/opt 172.16.238.10(rw,sync,no_subtree_check,no_root_squash,fsid=0)
/opt 172.16.238.11(rw,sync,no_subtree_check,no_root_squash,fsid=0)
/opt 172.16.238.12(rw,sync,no_subtree_check,no_root_squash,fsid=0)
exportds -av
exportfs -av
systemctl start nfs-server && systemctl start rpcbind
exportds -av
exportfs -av
systemctl status nfs-server && systemctl status rpcbind
showmount -e ststor01
df -h
ll -lsd /nfsshare/
ll /nfsshare




Log in to stapp01

systemctl status nfs-server && systemctl status rpcbind
systemctl start nfs-server && systemctl start rpcbind
systemctl status nfs-server && systemctl status rpcbind
showmount -e ststor01
mount -t nfs ststor01:/nfsshare /var/www/html
df -h
cd /var/www/html
ll
touch file01
ll

BACK TO ststor01
ll /nfsshare
