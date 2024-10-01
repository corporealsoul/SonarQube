### 1. BACKUP with Thinbackup
Thin Backup , http://192.168.56.102:8080/manage/configure

Backup directory - /var/lib/jenkins/backup
Backup schedule for full backups - H * * * *
Backup schedule for differential backups - H * * * *
Max number of backup sets - 1


### 2. Master Slave Configuration (Root user recomended )
Each slaves should have below configuarations,

[root@automation-and-continuous-delivery 08:39:10 ~]# sudo apt install fontconfig openjdk-17-jre[root@automation-and-continuous-delivery 08:39:10 ~]# java -version

[root@automation-and-continuous-delivery 08:39:10 ~]# sudo visudo

root    ALL=(ALL:ALL) ALL
anup    ALL=(ALL:ALL) NOPASSWD:ALL
jenkins ALL=(ALL:ALL) NOPASSWD:ALL

[root@automation-and-continuous-delivery 08:39:10 ~]# mkdir jenkins-slave
[root@automation-and-continuous-delivery 08:40:37 ~]# chmod 755 jenkins-slave/
[root@automation-and-continuous-delivery 08:39:22 ~]# cd jenkins-slave/




### -- Tools in Jenkins

### -- Freestyle project

### -- Tools in Jenkins

### -- Pipeline

### -- Security analysis


