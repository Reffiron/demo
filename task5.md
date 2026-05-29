task5

apt-get update && apt-get install –y ansible sshpass


conf 
/etc/ansible/hosts
br-rtr ansible_ssh_host=192.168.1.1 ansible_ssh_user=net_admin ansible_ssh_pass=P@ssword
hq-rtr ansible_ssh_host=172.16.1.2 ansible_ssh_user=net_admin ansible_ssh_pass=P@ssword
hq-srv ansible_ssh_host=192.168.100.2 ansible_ssh_user=sshuser ansible_ssh_pass=P@ssword ansible_ssh_port=2026
hq-cli ansible_ssh_host=192.168.200.2 ansible_ssh_user=Administrator@au-team.irpo ansible_ssh_pass=P@ssword

conf 
/etc/ansible/ansible.cfg
#host_key_checking = False >> host_key_checking = False
