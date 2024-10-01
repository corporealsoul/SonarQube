### Pre-requisites,
anup@infrustructure-management-and-provisioning:~$ java --version
anup@infrustructure-management-and-provisioning:~$ psql --version


### Configuration,
anup@infrustructure-management-and-provisioning:~$ su - postgres
Password: 6£t78,(EPHV<

postgres@infrustructure-management-and-provisioning:~$ createuser sonar
postgres@infrustructure-management-and-provisioning:~$ psql
postgres=# ALTER USER sonar WITH ENCRYPTED password 'N4V4e!02w2jq';
postgres'# CREATE DATABASE sonarqube OWNER sonar;
postgres'# GRANT ALL PRIVILEGES ON DATABASE sonarqube to sonar;
postgres'# \dl
postgres'# \l
postgres'# \q
Use control-D to quit.
postgres@infrustructure-management-and-provisioning:~$ exit


anup@infrustructure-management-and-provisioning:~$ sudo apt-get install zip -y

https://binaries.sonarsource.com/
https://binaries.sonarsource.com/?prefix=Distribution/
https://binaries.sonarsource.com/?prefix=Distribution/sonarqube/
https://binaries.sonarsource.com/Distribution/sonarqube/sonarqube-9.9.6.92038.zip
anup@infrustructure-management-and-provisioning:~$ wget https://binaries.sonarsource.com/Distribution/sonarqube/sonarqube-9.9.6.92038.zip
anup@infrustructure-management-and-provisioning:~$ unzip sonarqube-9.9.6.92038.zip
anup@infrustructure-management-and-provisioning:~$ sudo mv sonarqube-9.9.6.92038 /opt/sonarqube
anup@infrustructure-management-and-provisioning:~$ ls -ltr
anup@infrustructure-management-and-provisioning:~$ sudo mv sonarqube-9.9.6.92038 /opt/sonarqube



anup@infrustructure-management-and-provisioning:~$ sudo groupadd sonar
anup@infrustructure-management-and-provisioning:~$ sudo useradd -d /opt/sonarqube -g sonar sonar
anup@infrustructure-management-and-provisioning:~$ sudo chown sonar:sonar /opt/sonarqube -R
anup@infrustructure-management-and-provisioning:~$ sudo nano /opt/sonarqube/conf/sonar.properties
sonar.jdbc.username=sonar
sonar.jdbc.password=N4V4e!02w2jq

sonar.jdbc.url=jdbc:postgresql://192.168.56.201:5432/sonarqube

sonar.search.javaOpts=-Xmx512m -Xms512m -XX:MaxDirectMemorySize=256m -XX:+HeapDumpOnOutOfMemoryError

sonar.web.host=192.168.56.101
sonar.web.port=9000
sonar.web.javaAdditionalOpts=-server
sonar.log.level=INFO
sonar.path.logs=logs

anup@infrustructure-management-and-provisioning:~$ ls -ltr /opt/sonarqube/bin/linux-x86-64/sonar.sh
anup@infrustructure-management-and-provisioning:~$ sudo nano /opt/sonarqube/bin/linux-x86-64/sonar.sh
RUN_AS_USER=sonar # add this line

anup@infrustructure-management-and-provisioning:~$ sudo nano /etc/systemd/system/sonar.service
[Unit]
Description=SonarQube service
After=syslog.target network.target

[Service]
Type=forking
User=sonar
Group=sonar
ExecStart=/opt/sonarqube/bin/linux-x86-64/sonar.sh start
ExecStop=/opt/sonarqube/bin/linux-x86-64/sonar.sh stop
StandardOutput=journal
LimitNOFILE=131072
LimitNPROC=8192
TimeoutStartSec=5
Restart=always
SuccessExitStatus=143

[Install]
WantedBy=multi-user.target

anup@infrustructure-management-and-provisioning:~$ sudo systemctl daemon-reload
anup@infrustructure-management-and-provisioning:~$ sudo systemctl enable sonar
anup@infrustructure-management-and-provisioning:~$ sudo systemctl start sonar
anup@infrustructure-management-and-provisioning:~$ sudo systemctl status sonar

anup@infrustructure-management-and-provisioning:~$ sudo nano /etc/sysctl.conf
vm.max_map_count=262144
fs.file-max=65536
ulimit -n 131072
ulimit -u 8192

anup@infrustructure-management-and-provisioning:~$ sudo nano /etc/security/limits.d/99-sonarqube.conf
sonarqube       -       nofile  131072
sonarqube       -       nproc   8192

anup@infrustructure-management-and-provisioning:~$ sudo reboot now

anup@infrustructure-management-and-provisioning:~$ sudo ufw allow 9000/tcp
anup@infrustructure-management-and-provisioning:~$ sudo ufw status

anup@infrustructure-management-and-provisioning:/opt/sonarqube/logs$ cat sonar.log
anup@infrustructure-management-and-provisioning:/opt/sonarqube/logs$ cat es.log
anup@infrustructure-management-and-provisioning:/opt/sonarqube/logs$ tail -f sonar.log

anup@infrustructure-management-and-provisioning:/opt/sonarqube/logs$ netstat -tunlp | grep LISTEN

anup@infrustructure-management-and-provisioning:~$ sudo apt-get install nginx -y
anup@infrustructure-management-and-provisioning:~$ sudo systemctl is-enabled nginx
anup@infrustructure-management-and-provisioning:~$ sudo systemctl status nginx
anup@infrustructure-management-and-provisioning:~$ sudo nano /etc/nginx/sites-available/sonarqube.conf
server {

    listen 80;
    server_name sonar.hwdomain.io;
    access_log /var/log/nginx/sonar.access.log;
    error_log /var/log/nginx/sonar.error.log;
    proxy_buffers 16 64k;
    proxy_buffer_size 128k;

    location / {
        proxy_pass http://192.168.56.101:9000;
        proxy_next_upstream error timeout invalid_header http_500 http_502 http_503 http_504;
        proxy_redirect off;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto http;
    }
}

anup@infrustructure-management-and-provisioning:~$ sudo ln -s /etc/nginx/sites-available/sonarqube.conf /etc/nginx/sites-enabled/
anup@infrustructure-management-and-provisioning:~$ sudo nginx -t
anup@infrustructure-management-and-provisioning:~$ sudo systemctl restart nginx
anup@infrustructure-management-and-provisioning:~$ sudo systemctl status nginx


http://192.168.56.101:9000/

Id : admin
Password : N4V4e!02w2jq



### Docker Installation,
https://hub.docker.com/_/sonarqube/


anup@infrustructure-management-and-provisioning:~/Jenkins$ sudo apt update && sudo apt -y full-upgrade
anup@infrustructure-management-and-provisioning:~/Jenkins$ sudo reboot now
anup@infrustructure-management-and-provisioning:~/Jenkins$ sudo apt install curl gpg gnupg2 software-properties-common apt-transport-https lsb-release ca-certificates


https://docs.docker.com/engine/install/ubuntu/
anup@automation-and-continuous-delivery:~$ sudo systemctl enable docker.service
anup@automation-and-continuous-delivery:~$ sudo systemctl start docker.service
anup@automation-and-continuous-delivery:~$ sudo systemctl status docker.service
anup@automation-and-continuous-delivery:~$ docker --version

anup@automation-and-continuous-delivery:~$ sudo apt install docker-compose
anup@automation-and-continuous-delivery:~$ docker-compose --version


### With docker image
anup@automation-and-continuous-delivery:~$ docker run -d --name sonar -p 9000:9000 sonarqube:lts-community
anup@automation-and-continuous-delivery:~$ docker ps
anup@automation-and-continuous-delivery:~$ docker ps -a
anup@automation-and-continuous-delivery:~$ docker logs sonar
anup@automation-and-continuous-delivery:~$ docker stats sonar

[anup@infrustructure-management-and-provisioning 10:39:41 ~]$ docker start sonar

http://192.168.56.101:9000/

Id : admin
Password : N4V4e!02w2jq

Generate Tokens
Nanme : admin
Token : squ_9603d90e95e8c5f9215cd8e53c32a662a6a0db06



### With docker compose
https://github.com/SonarSource/docker-sonarqube/blob/master/example-compose-files/sq-with-postgres/docker-compose.yml

anup@automation-and-continuous-delivery:~$ nano docker-compose.yml
anup@automation-and-continuous-delivery:~$ docker-compose up -d
anup@automation-and-continuous-delivery:~$ docker ps -a

