https://binaries.sonarsource.com/?prefix=Distribution/sonar-scanner-cli/

[anup@infrustructure-management-and-provisioning 09:50:09 ~]$ wget https://binaries.sonarsource.com/Distribution/sonar-scanner-cli/sonar-scanner-cli-6.1.0.4477-linux-x64.zip

[anup@infrustructure-management-and-provisioning 09:53:39 ~]$ sudo unzip sonar-scanner-cli-6.1.0.4477-linux-x64.zip -d /opt

[anup@infrustructure-management-and-provisioning 09:56:16 ~]$ nano .bashrc
#SONAR_SCANNER_HOME
export SONAR_SCANNER_HOME=/opt/sonar-scanner-6.1.0.4477-linux-x64
export PATH="$PATH:$SONAR_SCANNER_HOME/bin"

[anup@infrustructure-management-and-provisioning 09:58:53 ~]$ source ~/.bashrc
[anup@infrustructure-management-and-provisioning 09:59:30 ~]$ sonar-scanner -v

