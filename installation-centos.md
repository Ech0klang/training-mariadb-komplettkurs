# Installation Centos / Rocky Linux 

## Install from Distribution 


```
dnf search mariadb
# find version 
dnf info mariadb-server 
dnf install -y mariadb-server 
```


## Install from MariaDB Foundation (Repo) 

### Find Repo Settings 

  * https://mariadb.org/download/?t=mariadb&p=mariadb&r=10.9.3&os=windows&cpu=x86_64&pkg=msi&m=hs-esslingen


### Setup Repo MariaDB - Server 10.6

```
# Setup repo 
# nano /etc/yum.repos.d/MariaDB.repo
```

```
# MariaDB 10.6 CentOS repository list - created 2022-09-20 09:46 UTC
# https://mariadb.org/download/
[mariadb]
name = MariaDB
baseurl = https://mirror1.hs-esslingen.de/pub/Mirrors/mariadb/yum/10.6/centos8-amd64
module_hotfixes=1
gpgkey=https://mirror1.hs-esslingen.de/pub/Mirrors/mariadb/yum/RPM-GPG-KEY-MariaDB
gpgcheck=1
```

```
# Install
sudo dnf install -y install MariaDB-server
sudo systemctl start mysql # always works - systemd - alias 
sudo systemctl status mysql # Findout real service - name
# like Windows-Autostart
sudo systemctl enable mariadb  
sudo systemctl status mariadb 
```


## Secure installation 

```
mariadb-secure-installation 
# OR: if not present before 10.4 
mysql_secure_installation 
```
