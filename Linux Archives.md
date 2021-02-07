On Nautilus storage server in Stratos DC there is a storage location /data which is used by different developers to keep their data (no confidential data). One of the developer kazeem has raised a ticket and asked for a copy of his/her data present in /data/kazeem directory on storage server. /home is an FTP location on storage server from where developers can download their data. Below are the instructions shared by system admin team to accomplish the task:

Make a kazeem.tar.gz compressed archive of /data/kazeem directory and move the archive to /home directory on storage server.

ssh natasha@ststor01
sudo su -
ll -lsd /data/kazeem/
tar -czvf kazeem.tar.gz /data/kazeem
ll
mv kazeem.tar.gz /home/
ll /home/
