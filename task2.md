task2
HQ-SRV
apt-get install –y mdadm


mdadm --create /dev/md0 –l 0 –n 2 /dev/sdb /dev/sdc

mdadm --detail --scan --verbose | tee -a /etc/mdadm.conf

mkfs.ext4 /dev/md0

conf 
 /etc/fstab
/dev/md0    /raid    ext4    defaults    0    0


mkdir /raid

mount -av

lsblk
