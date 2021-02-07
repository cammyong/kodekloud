xFusionCorp Industries has an application running on Nautlitus infrastructure in Stratos Datacenter. The monitoring tool recognised that there is an issue with the haproxy service on LBR server. That need to fixed to make the application work properly.


Troubleshoot and fix the issue, and make sure haproxy service is running on Nautilus LBR server.


       systemctl start haproxy
       systemctl enable haproxy
       systemctl status haproxy -l
       cd /etc/haproxy/
       haproxy -c -f haproxy.cfg       
       vi haproxy.cfg
					         	
      # error
      REMOVE # BEFORE backend app
      systemctl restart haproxy
      systemctl status haproxy -l
