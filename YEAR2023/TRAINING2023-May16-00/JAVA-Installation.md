anup@automation-and-continuous-delivery:~$ java --version
anup@automation-and-continuous-delivery:~$ javac --version
anup@automation-and-continuous-delivery:~$ mvn --version

APT Installation,
anup@automation-and-continuous-delivery:~$ sudo apt install fontconfig openjdk-17-jre
anup@automation-and-continuous-delivery:~$ sudo apt install openjdk-17-jdk-headless
anup@automation-and-continuous-delivery:~$ readlink -f $(which java)
/usr/lib/jvm/java-17-openjdk-amd64/bin/java
anup@automation-and-continuous-delivery:~$ sudo nano ~/.bashrc
#JAVA_HOME
export JAVA_HOME=/usr/lib/jvm/java-17-openjdk-amd64
export PATH="$PATH:$JAVA_HOME/bin"

anup@automation-and-continuous-delivery:~$ source ~/.bashrc
anup@automation-and-continuous-delivery:~$ echo $JAVA_HOME
anup@automation-and-continuous-delivery:~$ echo $PATH
anup@automation-and-continuous-delivery:~$ java --version
anup@automation-and-continuous-delivery:~$ javac --version


Manual Installation,
https://www.oracle.com/java/technologies/downloads/
anup@automation-and-continuous-delivery:~$ wget https://download.oracle.com/java/21/latest/jdk-21_linux-x64_bin.deb
anup@automation-and-continuous-delivery:~$ sudo dpkg -i jdk-21_linux-x64_bin.deb
anup@automation-and-continuous-delivery:~$ sudo update-alternatives --config 'java'
anup@automation-and-continuous-delivery:~$ sudo update-alternatives --config 'javac'
anup@automation-and-continuous-delivery:~$ readlink -f $(which java)
anup@automation-and-continuous-delivery:~$ sudo nano ~/.bashrc
#JAVA_HOME
export JAVA_HOME=/usr/lib/jvm/jdk-21.0.4-oracle-x64
export PATH="$PATH:$JAVA_HOME/bin"

anup@automation-and-continuous-delivery:~$ source ~/.bashrc
anup@automation-and-continuous-delivery:~$ echo $JAVA_HOME
anup@automation-and-continuous-delivery:~$ echo $PATH
anup@automation-and-continuous-delivery:~$ java --version
anup@automation-and-continuous-delivery:~$ javac --version



