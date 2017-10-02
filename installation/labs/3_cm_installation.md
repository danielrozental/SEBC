```
[root@ip-172-31-11-253 mariadb]# mysql -u root -p
Enter password:
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 9
Server version: 5.5.56-MariaDB MariaDB Server

Copyright (c) 2000, 2017, Oracle, MariaDB Corporation Ab and others.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

MariaDB [(none)]> create database amon DEFAULT CHARACTER SET utf8;
grant all on amon.* TO 'amon'@'%' IDENTIFIED BY 'amon_password';
create database rman DEFAULT CHARACTER SET utf8;
grant all on rman.* TO 'rman'@'%' IDENTIFIED BY 'rman_password';
create databQuery OK, 1 row affected (0.00 sec)
ase metast
ore DEFAULT CHARACTER SET utf8;
MariaDB [(none)]> grant all on amon.* TO 'amon'@'%' IDENTIFIED BY 'amon_password';
grant all on metastore.* TO 'hive'@'%' IDENTIFIED BY 'hive_password';
create database sentry DEFAULT CHARACTER SET utf8;
grant all on sentry.* TO 'sentry'@'%' IDENTIFIED BY 'sentry_password';
create database nav DEFAULT CHARACTER SET utf8;
grant all on nav.* TO 'nav'@'%' IDENTIFIED BY 'nav_password';
create database navms DEFAULT CHARACTER SET utf8;
grant all on navms.* TO 'navmsQuery OK, 0 rows affected (0.00 sec)'
@'%'
 IDENTIFIED BY 'navms_password';
MariaDB [(none)]> create database rman DEFAULT CHARACTER SET utf8;

create database scm DEFAULT CHARACTER SET utf8;
grant all on scm.* TO 'scm'@'%' IDENTIFIED BY 'scm_password';

creaQuery OK, 1 row affected (0.00 sec)
te datab
ase hue;
grant all on hue.* to 'hue'@'%' identified by 'sMariaDB [(none)]> grant all on rman.* TO 'rman'@'%' IDENTIFIED BY 'rman_password';
Query OK, 0 rows affected (0.00 sec)

MariaDB [(none)]> create database metastore DEFAULT CHARACTER SET utf8;
Query OK, 1 row affected (0.00 sec)

MariaDB [(none)]> grant all on metastore.* TO 'hive'@'%' IDENTIFIED BY 'hive_password';
Query OK, 0 rows affected (0.00 sec)

MariaDB [(none)]> create database sentry DEFAULT CHARACTER SET utf8;
Query OK, 1 row affected (0.00 sec)

MariaDB [(none)]> grant all on sentry.* TO 'sentry'@'%' IDENTIFIED BY 'sentry_password';
Query OK, 0 rows affected (0.00 sec)

MariaDB [(none)]> create database nav DEFAULT CHARACTER SET utf8;
Query OK, 1 row affected (0.01 sec)

MariaDB [(none)]> grant all on nav.* TO 'nav'@'%' IDENTIFIED BY 'nav_password';
Query OK, 0 rows affected (0.00 sec)

MariaDB [(none)]> create database navms DEFAULT CHARACTER SET utf8;
Query OK, 1 row affected (0.00 sec)

MariaDB [(none)]> grant all on navms.* TO 'navms'@'%' IDENTIFIED BY 'navms_password';
Query OK, 0 rows affected (0.00 sec)

MariaDB [(none)]>
MariaDB [(none)]> create database scm DEFAULT CHARACTER SET utf8;
Query OK, 1 row affected (0.00 sec)

MariaDB [(none)]> grant all on scm.* TO 'scm'@'%' IDENTIFIED BY 'scm_password';
Query OK, 0 rows affected (0.00 sec)

MariaDB [(none)]>
MariaDB [(none)]> create database hue;
Query OK, 1 row affected (0.00 sec)

MariaDB [(none)]> grant all on hue.* to 'hue'@'%' identified by 'secretpassword';
Query OK, 0 rows affected (0.00 sec)

MariaDB [(none)]>
MariaDB [(none)]> create database oozie;
Query OK, 1 row affected (0.00 sec)

MariaDB [(none)]> grant all privileges on oozie.* to 'oozie'@'localhost' identified by 'oozie';
Query OK, 0 rows affected (0.00 sec)

MariaDB [(none)]> grant all privileges on oozie.* to 'oozie'@'%' identified by 'oozie';
Query OK, 0 rows affected (0.00 sec)
```


Instalo JDBC en todos los nodos

```
[root@ip-172-31-11-253 mariadb]# mkdir -p /usr/share/java
cd /tmp
wget -q https://dev.mysql.com/get/Downloads/Connector-J/mysql-connector-java-5.1.41.tar.gz
tar xf mysql-connector-java-5.1.41.tar.gz
cp mysql-connector-java-5.1.41/mysql-connector-java-5.1.41-bin.jar /usr/share/java/mysql-connector-java.jar
rm -rf /tmp/mysql-connector*
[root@ip-172-31-11-253 mariadb]# cd /tmp
[root@ip-172-31-11-253 tmp]# wget -q https://dev.mysql.com/get/Downloads/Connector-J/mysql-connector-java-5.1.41.tar.gz
[root@ip-172-31-11-253 tmp]# tar xf mysql-connector-java-5.1.41.tar.gz
[root@ip-172-31-11-253 tmp]# cp mysql-connector-java-5.1.41/mysql-connector-java-5.1.41-bin.jar /usr/share/java/mysql-connector-java.jar
[root@ip-172-31-11-253 tmp]# rm -rf /tmp/mysql-connector*
```

```
[root@ip-172-31-11-253 tmp]# cd /etc/yum.repos.d/
[root@ip-172-31-11-253 yum.repos.d]# wget https://archive.cloudera.com/cm5/redhat/7/x86_64/cm/cloudera-manager.repo
--2017-10-02 18:12:38--  https://archive.cloudera.com/cm5/redhat/7/x86_64/cm/cloudera-manager.repo
Resolving archive.cloudera.com (archive.cloudera.com)... 151.101.32.167
Connecting to archive.cloudera.com (archive.cloudera.com)|151.101.32.167|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 290
Saving to: ‘cloudera-manager.repo’

100%[=====================================>] 290         --.-K/s   in 0s

2017-10-02 18:12:38 (69.6 MB/s) - ‘cloudera-manager.repo’ saved [290/290]
```

```
[root@ip-172-31-11-253 yum.repos.d]# vi cloudera-manager.repo
[root@ip-172-31-11-253 yum.repos.d]# cat cloudera-manager.repo
[cloudera-manager]
# Packages for Cloudera Manager, Version 5, on RedHat or CentOS 7 x86_64       
name=Cloudera Manager
baseurl=https://archive.cloudera.com/cm5/redhat/7/x86_64/cm/5.9/
gpgkey =https://archive.cloudera.com/cm5/redhat/7/x86_64/cm/RPM-GPG-KEY-cloudera
gpgcheck = 1
```

```
[root@ip-172-31-11-253 yum.repos.d]# yum install oracle-j2sdk1.7
Loaded plugins: fastestmirror
cloudera-manager                                        |  951 B     00:00
cloudera-manager/primary                                  | 4.3 kB   00:00
Loading mirror speeds from cached hostfile
 * base: mirrors.usinternet.com
 * extras: mirror.math.princeton.edu
 * updates: centos.aol.com
cloudera-manager                                                           7/7
Resolving Dependencies
--> Running transaction check
---> Package oracle-j2sdk1.7.x86_64 0:1.7.0+update67-1 will be installed
--> Finished Dependency Resolution

Dependencies Resolved

===============================================================================
 Package            Arch      Version                Repository           Size
===============================================================================
Installing:
 oracle-j2sdk1.7    x86_64    1.7.0+update67-1       cloudera-manager    135 M

Transaction Summary
===============================================================================
Install  1 Package

Total download size: 135 M
Installed size: 279 M
Is this ok [y/d/N]: y
Downloading packages:
warning: /var/cache/yum/x86_64/7/cloudera-manager/packages/oracle-j2sdk1.7-1.7.0+update67-1.x86_64.rpm: Header V4 DSA/SHA1 Signature, key ID e8f86acd: NOKEY
Public key for oracle-j2sdk1.7-1.7.0+update67-1.x86_64.rpm is not installed
oracle-j2sdk1.7-1.7.0+update67-1.x86_64.rpm               | 135 MB   00:06
Retrieving key from https://archive.cloudera.com/cm5/redhat/7/x86_64/cm/RPM-GPG-KEY-cloudera
Importing GPG key 0xE8F86ACD:
 Userid     : "Yum Maintainer <webmaster@cloudera.com>"
 Fingerprint: 5f14 d39e f068 1aca 6f04 4a43 f90c 0d8f e8f8 6acd
 From       : https://archive.cloudera.com/cm5/redhat/7/x86_64/cm/RPM-GPG-KEY-cloudera
Is this ok [y/N]: y
Running transaction check
Running transaction test
Transaction test succeeded
Running transaction
  Installing : oracle-j2sdk1.7-1.7.0+update67-1.x86_64                     1/1
  Verifying  : oracle-j2sdk1.7-1.7.0+update67-1.x86_64                     1/1

Installed:
  oracle-j2sdk1.7.x86_64 0:1.7.0+update67-1

Complete!
```

```
[root@ip-172-31-11-253 yum.repos.d]# yum install cloudera-manager-daemons cloudera-manager-server
Installed:
  cloudera-manager-daemons.x86_64 0:5.9.3-1.cm593.p0.6.el7
  cloudera-manager-server.x86_64 0:5.9.3-1.cm593.p0.6.el7

Complete!
```


sudo service cloudera-scm-server start
