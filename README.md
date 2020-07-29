# aiok8s
This playbook will install an all-in-one k8s system

<bien@bienlab.com>

Before you start
----------------
create 'centos' user, adding public key and allow it to run as root without password
```
useradd centos
mkdir /home/centos/.ssh
chmod 700 /home/centos/.ssh
vi /home/centos/.ssh/authorized_keys
(adding your public key here)
chmod 400 /home/centos/.ssh/authorized_keys
chown -R centos:centos /home/centos/.ssh
echo "centos        ALL=(ALL)       NOPASSWD: ALL" > /etc/sudoers.d/centos
```
You may need to edit /etc/hosts as the below:
```
192.168.31.11 node1 node1.bienlab.com
```
Disable SELinux as well (if you want)
```
sed -i s/^SELINUX=.*$/SELINUX=disabled/ /etc/selinux/config
setenforce 0
```
On the ansible controll machine, 
- modify the ansible.cfg file
- modify the hosts file

Run they playbook
-----------------
```
ansible-playbook install_aiok8s.yml
```
If you like to install an offline aiok8s system:
```
ansible-playbook offline_install_aiok8s.yml
```
