change to the ansible install directory 
--> /etc/ansible 
you will see 3 files
a. ansible.cfg = ansible config settings
b. hosts = list of servers we will control , usually reffered to as inventory control
c. roles
change the hosts file
--> vim hosts
add the following to the file
[linux]
ip1
ip2
ip3
to add variable login add the below of ip3
linux = group referencing above
[linux:vars]

ansible_user = root (dont use root)
ansible_password = Password123 (dont use Password123)
:wq

vim ansible.cfg
uncomment #host_key_cheking = False
:wq

ansible linux -m ping
#used to confirm both machines are accessible.
ansible linux -a "cat /etc/os-release"
anisble linux -a "reboot"
-a means adhocs commands that you can do quick
playbook = used to yaml = data serialization language
