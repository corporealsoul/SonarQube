https://ubuntu.com/server/docs/install-and-configure-postgresql
https://www.postgresql.org/download/linux/ubuntu/


anup@infrustructure-management-and-provisioning:~/Jenkins/YEAR2023/TRAINING2023-May13-00$ sudo apt-get update
anup@infrustructure-management-and-provisioning:~/Jenkins/YEAR2023/TRAINING2023-May13-00$ sudo apt install curl ca-certificates
anup@infrustructure-management-and-provisioning:~/Jenkins/YEAR2023/TRAINING2023-May13-00$ sudo install -d /usr/share/postgresql-common/pgdg
anup@infrustructure-management-and-provisioning:~/Jenkins/YEAR2023/TRAINING2023-May13-00$ sudo curl -o /usr/share/postgresql-common/pgdg/apt.postgresql.org.asc --fail https://www.postgresql.org/media/keys/ACCC4CF8.asc
anup@infrustructure-management-and-provisioning:~/Jenkins/YEAR2023/TRAINING2023-May13-00$ sudo sh -c 'echo "deb [signed-by=/usr/share/postgresql-common/pgdg/apt.postgresql.org.asc] https://apt.postgresql.org/pub/repos/apt $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list'
anup@infrustructure-management-and-provisioning:~/Jenkins/YEAR2023/TRAINING2023-May13-00$ sudo apt update
anup@infrustructure-management-and-provisioning:~/Jenkins/YEAR2023/TRAINING2023-May13-00$ sudo apt install postgresql postgresql-contrib -y

anup@infrustructure-management-and-provisioning:~/Jenkins/YEAR2023/TRAINING2023-May13-00$ psql --version
anup@infrustructure-management-and-provisioning:~/Jenkins/YEAR2023/TRAINING2023-May13-00$ sudo systemctl status postgresql.service
anup@infrustructure-management-and-provisioning:~/Jenkins/YEAR2023/TRAINING2023-May13-00$ sudo systemctl enable postgresql.service

anup@infrustructure-management-and-provisioning:~/Jenkins/YEAR2023/TRAINING2023-May13-00$ sudo passwd postgres
New password: 6£t78,(EPHV<
Retype new password: 6£t78,(EPHV<




## Specific version
anup@infrustructure-management-and-provisioning:~/Jenkins$ sudo apt update && sudo apt -y full-upgrade
anup@infrustructure-management-and-provisioning:~/Jenkins$ sudo reboot now
anup@infrustructure-management-and-provisioning:~/Jenkins$ sudo apt install curl gpg gnupg2 software-properties-common apt-transport-https lsb-release ca-certificates
anup@infrustructure-management-and-provisioning:~/Jenkins$ curl -fsSL https://www.postgresql.org/media/keys/ACCC4CF8.asc|sudo gpg --dearmor -o /etc/apt/trusted.gpg.d/postgresql.gpg
anup@infrustructure-management-and-provisioning:~/Jenkins$ echo "deb http://apt.postgresql.org/pub/repos/apt/ `lsb_release -cs`-pgdg main" |sudo tee  /etc/apt/sources.list.d/pgdg.list
anup@infrustructure-management-and-provisioning:~/Jenkins$ sudo apt install postgresql-13 postgresql-client-13

anup@infrustructure-management-and-provisioning:~/Jenkins$ sudo systemctl status postgresql.service
anup@infrustructure-management-and-provisioning:~/Jenkins$ sudo systemctl enable postgresql.service

anup@infrustructure-management-and-provisioning:~/Jenkins$ psql --version

anup@infrustructure-management-and-provisioning:~/Jenkins$ createuser sonar
anup@infrustructure-management-and-provisioning:~/Jenkins$ su - postgres
anup@infrustructure-management-and-provisioning:~/Jenkins$ sudo passwd postgres
New password: 6£t78,(EPHV<
Retype new password: 6£t78,(EPHV<









