# Install tools

yum -y install net-tools
yum -y install bind-utils ntp nscd
yum -y install wget


#1. Swappiness
[root@ip-172-31-11-253 disco1]# cat /proc/sys/vm/swappiness
30

swappiness está en 30, lo cambio a 1

[root@ip-172-31-11-253 disco1]# sysctl -w vm.swappiness=1
vm.swappiness = 1
[root@ip-172-31-11-253 disco1]# cat /proc/sys/vm/swappiness                    1
1

# 2. Mount atributes

## Nodo 1

[root@ip-172-31-11-253 disco1]# df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       50G  2.3G   48G   5% /
devtmpfs         16G     0   16G   0% /dev
tmpfs            16G     0   16G   0% /dev/shm
tmpfs            16G   17M   16G   1% /run
tmpfs            16G     0   16G   0% /sys/fs/cgroup
tmpfs           3.2G     0  3.2G   0% /run/user/1000
/dev/xvdc       118G   61M  112G   1% /disco2
/dev/xvdb       118G   61M  112G   1% /disco1

## Nodo 2

[root@ip-172-31-6-79 centos]# df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       50G  2.3G   48G   5% /
devtmpfs         16G     0   16G   0% /dev
tmpfs            16G     0   16G   0% /dev/shm
tmpfs            16G   17M   16G   1% /run
tmpfs            16G     0   16G   0% /sys/fs/cgroup
/dev/xvdb       118G   61M  112G   1% /disco1
/dev/xvdc       118G   61M  112G   1% /disco2
tmpfs           3.2G     0  3.2G   0% /run/user/1000

## Nodo 3

[root@ip-172-31-9-51 centos]# df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       50G  2.3G   48G   5% /
devtmpfs         16G     0   16G   0% /dev
tmpfs            16G     0   16G   0% /dev/shm
tmpfs            16G   17M   16G   1% /run
tmpfs            16G     0   16G   0% /sys/fs/cgroup
/dev/xvdb       118G   61M  112G   1% /disco1
/dev/xvdc       118G   61M  112G   1% /disco2
tmpfs           3.2G     0  3.2G   0% /run/user/1000

## Nodo 4
[root@ip-172-31-1-236 centos]# df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       50G  2.3G   48G   5% /
devtmpfs         16G     0   16G   0% /dev
tmpfs            16G     0   16G   0% /dev/shm
tmpfs            16G   17M   16G   1% /run
tmpfs            16G     0   16G   0% /sys/fs/cgroup
/dev/xvdb       118G   61M  112G   1% /disco1
/dev/xvdc       118G   61M  112G   1% /disco2
tmpfs           3.2G     0  3.2G   0% /run/user/1000