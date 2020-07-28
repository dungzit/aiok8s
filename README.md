# aiok8s
This playbook will install an all-in-one k8s system

<bien@bienlab.com>


Before you start
----------------
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

modify the hosts file (inventory file)

modify the ansible.cfg file

Run they playbook
-----------------
```
ansible-playbook install_aiok8s.yml
```
