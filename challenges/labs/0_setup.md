# List the cloud provider you are using (AWS, GCE, Azure, CloudCat, other)

AWS

# List your instances by IP address and DNS name (don't use /etc/hosts for this)

```
Public Addresses
13.59.122.105	ec2-13-59-122-105.us-east-2.compute.amazonaws.com
13.58.7.252	ec2-13-58-7-252.us-east-2.compute.amazonaws.com
13.58.84.65	ec2-13-58-84-65.us-east-2.compute.amazonaws.com
13.58.2.117	ec2-13-58-2-117.us-east-2.compute.amazonaws.com

Private Addresses
172.31.35.178	ip-172-31-35-178.us-east-2.compute.internal
172.31.45.212	ip-172-31-45-212.us-east-2.compute.internal
172.31.35.215	ip-172-31-35-215.us-east-2.compute.internal
172.31.33.183	ip-172-31-33-183.us-east-2.compute.internal
```

# List the Linux release you are using

```
[root@ip-172-31-35-178 centos]# rpm --query centos-release
centos-release-7-2.1511.el7.centos.2.10.x86_64
```

# List the file system capacity for the first node

```
[root@ip-172-31-35-178 centos]# df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       50G  2.2G   48G   5% /
devtmpfs         16G     0   16G   0% /dev
tmpfs            16G     0   16G   0% /dev/shm
tmpfs            16G   17M   16G   1% /run
tmpfs            16G     0   16G   0% /sys/fs/cgroup
tmpfs           3.2G     0  3.2G   0% /run/user/1000
/dev/xvdb       118G   61M  112G   1% /disco1
/dev/xvdc       118G   61M  112G   1% /disco2
```

# List the command and output for yum repolist enabled

```
[root@ip-172-31-35-178 centos]# yum repolist enabled
Loaded plugins: fastestmirror
Repodata is over 2 weeks old. Install yum-cron? Or run: yum makecache fast
Determining fastest mirrors
 * base: distro.ibiblio.org
 * extras: mirrors.gigenet.com
 * updates: mirrors.gigenet.com
repo id                             repo name                             status
!base/7/x86_64                      CentOS-7 - Base                       9,007
!extras/7/x86_64                    CentOS-7 - Extras                       226
!updates/7/x86_64                   CentOS-7 - Updates                      856
repolist: 10,089
```

```
[root@ip-172-31-45-212 centos]# yum repolist enabled
Loaded plugins: fastestmirror
Repodata is over 2 weeks old. Install yum-cron? Or run: yum makecache fast
Determining fastest mirrors
 * base: ftp.linux.ncsu.edu
 * extras: mirrors.gigenet.com
 * updates: mirrors.gigenet.com
repo id                             repo name                            status
!base/7/x86_64                      CentOS-7 - Base                      9,007
!extras/7/x86_64                    CentOS-7 - Extras                      226
!updates/7/x86_64                   CentOS-7 - Updates                     856
repolist: 10,089
```

```
[root@ip-172-31-35-215 centos]# yum repolist enabled
Loaded plugins: fastestmirror
Repodata is over 2 weeks old. Install yum-cron? Or run: yum makecache fast
Determining fastest mirrors
 * base: ftp.linux.ncsu.edu
 * extras: mirrors.gigenet.com
 * updates: mirrors.gigenet.com
repo id                             repo name                             status
!base/7/x86_64                      CentOS-7 - Base                       9,007
!extras/7/x86_64                    CentOS-7 - Extras                       226
!updates/7/x86_64                   CentOS-7 - Updates                      856
repolist: 10,089
```

```
[root@ip-172-31-33-183 centos]# yum repolist enabled
Loaded plugins: fastestmirror
Repodata is over 2 weeks old. Install yum-cron? Or run: yum makecache fast
Determining fastest mirrors
 * base: distro.ibiblio.org
 * extras: mirrors.liquidweb.com
 * updates: mirrors.liquidweb.com
repo id                             repo name                             status
!base/7/x86_64                      CentOS-7 - Base                       9,007
!extras/7/x86_64                    CentOS-7 - Extras                       226
!updates/7/x86_64                   CentOS-7 - Updates                      856
repolist: 10,089
```

# Add the following Linux accounts to all nodes
[root@ip-172-31-35-178 centos]# useradd saturn -u 2800
[root@ip-172-31-35-178 centos]# useradd haley -u 2900
[root@ip-172-31-35-178 centos]#
[root@ip-172-31-35-178 centos]# groupadd comets
[root@ip-172-31-35-178 centos]# usermod -a -G comets haley
[root@ip-172-31-35-178 centos]#
[root@ip-172-31-35-178 centos]# groupadd planets
[root@ip-172-31-35-178 centos]# usermod -a -G planets saturn
[root@ip-172-31-35-178 centos]#
[root@ip-172-31-35-178 centos]# cat /etc/passwd | grep -E "saturn|haley"
saturn:x:2800:2800::/home/saturn:/bin/bash
haley:x:2900:2900::/home/haley:/bin/bash
[root@ip-172-31-35-178 centos]#
[root@ip-172-31-35-178 centos]# cat /etc/group | grep -E "comets|planets"
comets:x:2901:haley
planets:x:2902:saturn

[root@ip-172-31-45-212 centos]# useradd saturn -u 2800
[root@ip-172-31-45-212 centos]# useradd haley -u 2900
[root@ip-172-31-45-212 centos]#
[root@ip-172-31-45-212 centos]# groupadd comets
[root@ip-172-31-45-212 centos]# usermod -a -G comets haley
[root@ip-172-31-45-212 centos]#
[root@ip-172-31-45-212 centos]# groupadd planets
[root@ip-172-31-45-212 centos]# usermod -a -G planets saturn
[root@ip-172-31-45-212 centos]#
[root@ip-172-31-45-212 centos]# cat /etc/passwd | grep -E "saturn|haley"
saturn:x:2800:2800::/home/saturn:/bin/bash
haley:x:2900:2900::/home/haley:/bin/bash
[root@ip-172-31-45-212 centos]#
[root@ip-172-31-45-212 centos]# cat /etc/group | grep -E "comets|planets"
comets:x:2901:haley
planets:x:2902:saturn

[root@ip-172-31-35-215 centos]# useradd saturn -u 2800
[root@ip-172-31-35-215 centos]# useradd haley -u 2900
[root@ip-172-31-35-215 centos]#
[root@ip-172-31-35-215 centos]# groupadd comets
[root@ip-172-31-35-215 centos]# usermod -a -G comets haley
[root@ip-172-31-35-215 centos]#
[root@ip-172-31-35-215 centos]# groupadd planets
[root@ip-172-31-35-215 centos]# usermod -a -G planets saturn
[root@ip-172-31-35-215 centos]#
[root@ip-172-31-35-215 centos]# cat /etc/passwd | grep -E "saturn|haley"
saturn:x:2800:2800::/home/saturn:/bin/bash
haley:x:2900:2900::/home/haley:/bin/bash
[root@ip-172-31-35-215 centos]#
[root@ip-172-31-35-215 centos]# cat /etc/group | grep -E "comets|planets"
comets:x:2901:haley
planets:x:2902:saturn

[root@ip-172-31-33-183 centos]# useradd saturn -u 2800
[root@ip-172-31-33-183 centos]# useradd haley -u 2900
[root@ip-172-31-33-183 centos]#
[root@ip-172-31-33-183 centos]# groupadd comets
[root@ip-172-31-33-183 centos]# usermod -a -G comets haley
[root@ip-172-31-33-183 centos]#
[root@ip-172-31-33-183 centos]# groupadd planets
[root@ip-172-31-33-183 centos]# usermod -a -G planets saturn
[root@ip-172-31-33-183 centos]#
[root@ip-172-31-33-183 centos]# cat /etc/passwd | grep -E "saturn|haley"
saturn:x:2800:2800::/home/saturn:/bin/bash
haley:x:2900:2900::/home/haley:/bin/bash
[root@ip-172-31-33-183 centos]#
[root@ip-172-31-33-183 centos]# cat /etc/group | grep -E "comets|planets"
comets:x:2901:haley
planets:x:2902:saturn

