The backup server in the Stratos DC contains several template XML files used by the Nautilus application. These template XML files must however be populated with valid data before it can be used. One of the daily tasks of a system admin working in the xFusionCorp industries, is to apply string and file manipulation commands!

Replace all occurences of the string About to Torpedo on the XML file /root/nautilus.xml located in the backup server.


ssh clint@stbkp01
cat /root/nautilus.xml |grep About
cat /root/nautilus.xml |grep About | wc -l
sed -i 's/About/Torpedo/g' /root/nautilus.xml
cat /root/nautilus.xml |grep Torpedo | wc -l
