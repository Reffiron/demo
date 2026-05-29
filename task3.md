task3

HQ-SRV

apt-get install nfs-server -y

mkdir /raid/nfs
chmod -R 777 /raid/nfs



conf 
 /etc/exports
/raid/nfs 192.168.200.0/28(rw)

exportfs -arv
systemctl enable --now nfs-server

HQ-CLI

mkdir /mnt/nfs
chmod -R 777 /mnt/nfs

conf
/etc/fstab
192.168.100.2:/raid/nfs /mnt/nfs nfs defaults 0 0

mount -av

df -h 
