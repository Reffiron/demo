task4
ISP

conf 
/etc/chrony.conf

#pool pool.ntp.org iburst 

server ntp0.ntp-servers.net iburst prefer minstratum 4
allow 0.0.0.0/0

local stratum 5
