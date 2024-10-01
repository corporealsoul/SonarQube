### Maven APT Installation
anup@automation-and-continuous-delivery:~$ sudo apt-get update
anup@automation-and-continuous-delivery:~$ sudo apt install maven -y
anup@automation-and-continuous-delivery:~$ mvn -version
anup@automation-and-continuous-delivery:~$ readlink -f $(which mvn)
/usr/share/maven/bin/mvn
anup@automation-and-continuous-delivery:~$ sudo nano ~/.bashrc
#M2_HOME
export M2_HOME=/usr/share/maven
export PATH="$PATH:$M2_HOME/bin"

anup@automation-and-continuous-delivery:/opt$ source ~/.bashrc
anup@automation-and-continuous-delivery:/opt$ echo $M2_HOME
anup@automation-and-continuous-delivery:/opt$ echo $PATH
anup@automation-and-continuous-delivery:/opt$ mvn --version


### Maven Manual Installation
https://maven.apache.org/download.cgi
anup@automation-and-continuous-delivery:~$ cd /opt/
anup@automation-and-continuous-delivery:/opt$ sudo wget https://dlcdn.apache.org/maven/maven-3/3.9.8/binaries/apache-maven-3.9.8-bin.tar.gz
anup@automation-and-continuous-delivery:/opt$ sudo tar -xvzf apache-maven-3.9.8-bin.tar.gz
anup@automation-and-continuous-delivery:/opt$ sudo nano ~/.bashrc
#M2_HOME
export M2_HOME=/opt/apache-maven-3.9.8
export PATH="$PATH:$M2_HOME/bin"

anup@automation-and-continuous-delivery:/opt$ source ~/.bashrc
anup@automation-and-continuous-delivery:/opt$ echo $M2_HOME
anup@automation-and-continuous-delivery:/opt$ echo $PATH
anup@automation-and-continuous-delivery:/opt$ mvn --version