We have one of our website up and running on our Nautilus infrastructure in Stratos DC. Our security team has raised a concern that right now Apache’s port i.e 5001 is open for all since there is no firewall installed on these hosts. So we have decided to add some security layer for these hosts and after discussions and recommendations we have come up with below given requirements:

   1  Install iptables and all its dependencies on each app host.

      2  Block incoming port 5001 on all apps for everyone except for LBR host.

         3  Make sure the rules should persist even after system reboot.




	 DO SAME PROCEDURES FOR ALL APP SERVERS
	 ```sh
	 ssh tony@stapp01
	 systemctl status iptables
	 yum install -y iptables-services
	 systemctl start iptables
	 systemctl enable iptables
	 systemctl status iptables
	 iptables -L
	 iptables -R INPUT 5 -p tcp --dport 5001 -s 172.16.238.14 -j ACCEPT
	 iptables -A INPUT -p tcp --destination-port 5001 -j DROP
	 service iptables save
	 systemctl restart iptables
	 systemctl status iptables



	 check with LBR server:
	 login to LBR server check with appservers if it is reached or not 
	 curl 172.16.238.10:5001
	 curl 172.16.238.11:5001
	 curl 172.16.238.12:5001
	 ```

