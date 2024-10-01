### User
anup@infrustructure-management-and-provisioning:~$ ssh-keygen

anup@infrustructure-management-and-provisioning:~$ ssh-copy-id anup@192.168.56.101
anup@infrustructure-management-and-provisioning:~$ ssh-copy-id anup@192.168.56.102
anup@infrustructure-management-and-provisioning:~$ ssh-copy-id anup@192.168.56.103

anup@infrustructure-management-and-provisioning:~$ ssh anup@192.168.56.101
anup@infrustructure-management-and-provisioning:~$ ssh anup@192.168.56.102
anup@infrustructure-management-and-provisioning:~$ ssh anup@192.168.56.103

anup@infrustructure-management-and-provisioning:~$ ssh anup@infrustructure-management-and-provisioning
anup@infrustructure-management-and-provisioning:~$ ssh anup@automation-and-continuous-delivery
anup@infrustructure-management-and-provisioning:~$ ssh anup@monitoring-and-observability


### Root
root@infrustructure-management-and-provisioning:~# passwd
root@infrustructure-management-and-provisioning:~# nano /etc/ssh/sshd_config
PermitRootLogin prohibit-password yes

root@infrustructure-management-and-provisioning:~# ssh-keygen
root@infrustructure-management-and-provisioning:~# ssh-copy-id root@192.168.56.101
root@infrustructure-management-and-provisioning:~# ssh-copy-id root@192.168.56.102
root@infrustructure-management-and-provisioning:~# ssh-copy-id root@192.168.56.103

root@infrustructure-management-and-provisioning:~# cd .ssh/
root@infrustructure-management-and-provisioning:~/.ssh# sudo nano authorized_keys

root@infrustructure-management-and-provisioning:~# ssh root@192.168.56.101
root@infrustructure-management-and-provisioning:~# ssh root@192.168.56.102
root@infrustructure-management-and-provisioning:~# ssh root@192.168.56.103

root@infrustructure-management-and-provisioning:~# ssh root@infrustructure-management-and-provisioning
root@infrustructure-management-and-provisioning:~# ssh root@automation-and-continuous-delivery
root@infrustructure-management-and-provisioning:~# ssh root@monitoring-and-observability


### If you get , "ERROR: Server rejected the 1 private key(s) for anup (credentialId:01b1b29b-4351-433e-9f42-d3fbb42a57c0/method:publickey)"

[anup@infrustructure-management-and-provisioning 07:38:34 .ssh]$ ssh-keygen -t ed25519

[anup@infrustructure-management-and-provisioning 08:23:31 .ssh]$ ssh-copy-id anup@192.168.56.101
[anup@infrustructure-management-and-provisioning 08:23:31 .ssh]$ ssh-copy-id anup@192.168.56.102
[anup@infrustructure-management-and-provisioning 08:23:31 .ssh]$ ssh-copy-id anup@192.168.56.103

[anup@infrustructure-management-and-provisioning 08:25:59 .ssh]$ ssh anup@192.168.56.101
[anup@infrustructure-management-and-provisioning 08:25:59 .ssh]$ ssh anup@192.168.56.102
[anup@infrustructure-management-and-provisioning 08:25:59 .ssh]$ ssh anup@192.168.56.103

[anup@infrustructure-management-and-provisioning 08:28:39 .ssh]$ ssh anup@infrustructure-management-and-provisioning
[anup@infrustructure-management-and-provisioning 08:28:39 .ssh]$ ssh anup@automation-and-continuous-delivery
[anup@infrustructure-management-and-provisioning 08:28:39 .ssh]$ ssh anup@monitoring-and-observability


### Color Terminal
anup@infrustructure-management-and-provisioning 16:40:36 ~ > nano .bashrc
#export PS1="\[\e[01;37m\][\[\e[0m\]\[\e[01;32m\]\u\[\e[0m\]\[\e[00;37m\]@\[\e[0m\]\[\e[01;34m\]\h\[\e[0m\]\[\e[00;37m\] \[\e[0m\]\[\e[00;37m\]\t\[\e[0m\]\[\e[01;37m\] \W]\\$ \[\e[0m\]"
#export PS1="\[\e[01;37m\][\[\e[0m\]\[\e[01;31m\]\u\[\e[0m\]\[\e[00;37m\]@\[\e[0m\]\[\e[01;34m\]\h\[\e[0m\]\[\e[00;37m\] \[\e[0m\]\[\e[00;37m\]\t\[\e[0m\]\[\e[01;37m\] \W]\\$ \[\e[0m\]"
#export PS1="\[\e[01;33m\]\u\[\e[0m\]\[\e[00;37m\]@\[\e[0m\]\[\e[01;36m\]\h\[\e[0m\]\[\e[00;37m\] \t \[\e[0m\]\[\e[01;35m\]\w\[\e[0m\]\[\e[01;37m\] > \[\e[0m\]"
#export PS1="\n\[\e[01;33m\]\u\[\e[0m\]\[\e[00;37m\]@\[\e[0m\]\[\e[01;36m\]\h\[\e[0m\]\[\e[00;37m\] \t \[\e[0m\]\[\e[01;35m\]\w\[\e[0m\]\[\e[01;37m\] \[\e[0m\]\n$ "


### Run shell command with Sudo
[anup@automation-and-continuous-delivery When-IM-at-SAP]$ sudo visudo
root    ALL=(ALL)       ALL
anup    ALL=(ALL)       ALL
jenkins ALL=(ALL)       NOPASSWD:ALL
























