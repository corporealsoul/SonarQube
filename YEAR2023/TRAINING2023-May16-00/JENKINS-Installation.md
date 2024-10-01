
### Installation
https://www.jenkins.io/doc/book/installing/linux/#red-hat-centos

[anup@automation-and-continuous-delivery When-IM-at-SAP]$ sudo systemctl enable jenkins
[anup@automation-and-continuous-delivery When-IM-at-SAP]$ sudo systemctl start jenkins
[anup@automation-and-continuous-delivery When-IM-at-SAP]$ sudo systemctl status jenkins

http://192.168.56.102:8080/

[anup@automation-and-continuous-delivery When-IM-at-SAP]$ sudo cat /var/lib/jenkins/secrets/initialAdminPassword

[anup@automation-and-continuous-delivery When-IM-at-SAP]$ sudo systemctl status firewalld.service
[anup@automation-and-continuous-delivery When-IM-at-SAP]$ sudo firewall-cmd --zone=public --add-port=8080/tcp 
[anup@automation-and-continuous-delivery When-IM-at-SAP]$ sudo firewall-cmd --reload
[anup@automation-and-continuous-delivery When-IM-at-SAP]$ sudo firewall-cmd --zone=public --list-ports


### Run shell command with Sudo
[anup@automation-and-continuous-delivery When-IM-at-SAP]$ sudo visudo
root    ALL=(ALL)       ALL
anup    ALL=(ALL)       ALL
jenkins ALL=(ALL)       NOPASSWD:ALL


### Create user to run ansible playbooks
[anup@automation-and-continuous-delivery playbooks]$ sudo useradd corporealsoul
[anup@automation-and-continuous-delivery playbooks]$ sudo passwd corporealsoul
[anup@automation-and-continuous-delivery playbooks]$ sudo usermod -aG wheel corporealsoul


### Ubuntu Installation,
https://www.jenkins.io/doc/book/installing/linux/#debianubuntu


[anup@infrustructure-management-and-provisioning 07:14:39 Jenkins]$ sudo systemctl status jenkins.service

http://192.168.56.101:8080/







