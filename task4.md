task4
ISP

conf 
/etc/chrony.conf

#pool pool.ntp.org iburst 

server ntp0.ntp-servers.net iburst prefer minstratum 4
allow 0.0.0.0/0

local stratum 5

systemctl restart chronyd

CLIENTS

apt-get update && apt-get install chrony -y



#pool pool.ntp.org iburst 


server 172.16.1.1 iburst

systemctl restart chronyd


check
chronyc sources


172.16.2.1
172.16.1.1
