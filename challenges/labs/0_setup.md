# List the cloud provider you are using (AWS, GCE, Azure, CloudCat, other)

AWS

# List your instances by IP address and DNS name (don't use /etc/hosts for this)

```
Public Addresses
18.220.92.53	ec2-18-220-92-53.us-east-2.compute.amazonaws.com
18.221.240.181	ec2-18-221-240-181.us-east-2.compute.amazonaws.com
18.220.110.75	ec2-18-220-110-75.us-east-2.compute.amazonaws.com
18.221.26.25	ec2-18-221-26-25.us-east-2.compute.amazonaws.com

Private Addresses
172.31.37.61	ip-172-31-37-61.us-east-2.compute.internal
172.31.38.69	ip-172-31-38-69.us-east-2.compute.internal
172.31.36.167	ip-172-31-36-167.us-east-2.compute.internal
172.31.43.182	ip-172-31-43-182.us-east-2.compute.internal
```

# List the Linux release you are using

```
[root@ip-172-31-38-69 centos]# rpm --query centos-release
centos-release-7-2.1511.el7.centos.2.10.x86_64
```

# List the file system capacity for the first node

```
[centos@ip-172-31-37-61 ~]$ df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       50G  2.2G   48G   5% /
devtmpfs         16G     0   16G   0% /dev
tmpfs            16G     0   16G   0% /dev/shm
tmpfs            16G   17M   16G   1% /run
tmpfs            16G     0   16G   0% /sys/fs/cgroup
/dev/xvdb       118G   61M  112G   1% /disco1
/dev/xvdc       118G   61M  112G   1% /disco2
tmpfs           3.2G     0  3.2G   0% /run/user/1000

```

# List the command and output for yum repolist enabled

```
[root@ip-172-31-37-61 centos]# yum repolist enabled
Loaded plugins: fastestmirror
Repodata is over 2 weeks old. Install yum-cron? Or run: yum makecache fast
Determining fastest mirrors
 * base: mirror.5ninesolutions.com
 * extras: mirror.genesisadaptive.com
 * updates: centos.mirror.constant.com
repo id                                repo name                                status
!base/7/x86_64                         CentOS-7 - Base                          9,007
!extras/7/x86_64                       CentOS-7 - Extras                          226
!updates/7/x86_64                      CentOS-7 - Updates                         856
repolist: 10,089
```

```
[root@ip-172-31-38-69 centos]# yum repolist enabled
Loaded plugins: fastestmirror
Repodata is over 2 weeks old. Install yum-cron? Or run: yum makecache fast
Determining fastest mirrors
 * base: repos.dfw.quadranet.com
 * extras: mirror.genesisadaptive.com
 * updates: centos.mirror.constant.com
repo id                             repo name                            status
!base/7/x86_64                      CentOS-7 - Base                      9,007
!extras/7/x86_64                    CentOS-7 - Extras                      226
!updates/7/x86_64                   CentOS-7 - Updates                     856
repolist: 10,089
```

```
[root@ip-172-31-36-167 centos]# yum repolist enabled
Loaded plugins: fastestmirror
Repodata is over 2 weeks old. Install yum-cron? Or run: yum makecache fast
Determining fastest mirrors
 * base: mirror.5ninesolutions.com
 * extras: mirror.5ninesolutions.com
 * updates: centos.mirror.constant.com
repo id                             repo name                            status
!base/7/x86_64                      CentOS-7 - Base                      9,007
!extras/7/x86_64                    CentOS-7 - Extras                      226
!updates/7/x86_64                   CentOS-7 - Updates                     856
repolist: 10,089
```

```
[root@ip-172-31-43-182 centos]# yum repolist enabled
Loaded plugins: fastestmirror
Repodata is over 2 weeks old. Install yum-cron? Or run: yum makecache fast
Determining fastest mirrors
 * base: repos.dfw.quadranet.com
 * extras: mirror.genesisadaptive.com
 * updates: centos.mirror.constant.com
repo id                                repo name                                status
!base/7/x86_64                         CentOS-7 - Base                          9,007
!extras/7/x86_64                       CentOS-7 - Extras                          226
!updates/7/x86_64                      CentOS-7 - Updates                         856
repolist: 10,089
```

# Add the following Linux accounts to all nodes

```
[root@ip-172-31-37-61 centos]# useradd saturn -u 2800
[root@ip-172-31-37-61 centos]# useradd haley -u 2900
[root@ip-172-31-37-61 centos]#
[root@ip-172-31-37-61 centos]# groupadd comets
[root@ip-172-31-37-61 centos]# usermod -a -G comets haley
[root@ip-172-31-37-61 centos]#
[root@ip-172-31-37-61 centos]# groupadd planets
[root@ip-172-31-37-61 centos]# usermod -a -G planets saturn
[root@ip-172-31-37-61 centos]#
```

```
[root@ip-172-31-38-69 centos]# useradd saturn -u 2800
[root@ip-172-31-38-69 centos]# useradd haley -u 2900
[root@ip-172-31-38-69 centos]#
[root@ip-172-31-38-69 centos]# groupadd comets
[root@ip-172-31-38-69 centos]# usermod -a -G comets haley
[root@ip-172-31-38-69 centos]#
[root@ip-172-31-38-69 centos]# groupadd planets
[root@ip-172-31-38-69 centos]# usermod -a -G planets saturn
[root@ip-172-31-38-69 centos]#
```

```
[root@ip-172-31-36-167 centos]# useradd saturn -u 2800
[root@ip-172-31-36-167 centos]# useradd haley -u 2900
[root@ip-172-31-36-167 centos]#
[root@ip-172-31-36-167 centos]# groupadd comets
[root@ip-172-31-36-167 centos]# usermod -a -G comets haley
[root@ip-172-31-36-167 centos]#
[root@ip-172-31-36-167 centos]# groupadd planets
[root@ip-172-31-36-167 centos]# usermod -a -G planets saturn
[root@ip-172-31-36-167 centos]#
```

```
[root@ip-172-31-43-182 centos]# useradd saturn -u 2800
[root@ip-172-31-43-182 centos]# useradd haley -u 2900
[root@ip-172-31-43-182 centos]#
[root@ip-172-31-43-182 centos]# groupadd comets
[root@ip-172-31-43-182 centos]# usermod -a -G comets haley
[root@ip-172-31-43-182 centos]#
[root@ip-172-31-43-182 centos]# groupadd planets
[root@ip-172-31-43-182 centos]# usermod -a -G planets saturn
[root@ip-172-31-43-182 centos]#
```

# List the /etc/passwd entries for saturn and haley

```
[root@ip-172-31-38-69 centos]# cat /etc/passwd | grep -E "saturn|haley"
saturn:x:2800:2800::/home/saturn:/bin/bash
haley:x:2900:2900::/home/haley:/bin/bash
```

```
[root@ip-172-31-37-61 centos]# cat /etc/passwd | grep -E "saturn|haley"
saturn:x:2800:2800::/home/saturn:/bin/bash
haley:x:2900:2900::/home/haley:/bin/bash
```

```
[root@ip-172-31-36-167 centos]# cat /etc/passwd | grep -E "saturn|haley"
saturn:x:2800:2800::/home/saturn:/bin/bash
haley:x:2900:2900::/home/haley:/bin/bash
```

```
[root@ip-172-31-43-182 centos]# cat /etc/passwd | grep -E "saturn|haley"
saturn:x:2800:2800::/home/saturn:/bin/bash
haley:x:2900:2900::/home/haley:/bin/bash
```

# List the /etc/group entries for comets and planets

```
[root@ip-172-31-38-69 centos]# cat /etc/group | grep -E "comets|planets"
comets:x:2901:haley
planets:x:2902:saturn
```

```
[root@ip-172-31-37-61 centos]# cat /etc/group | grep -E "comets|planets"
comets:x:2901:haley
planets:x:2902:saturn
```

```
[root@ip-172-31-36-167 centos]# cat /etc/group | grep -E "comets|planets"
comets:x:2901:haley
planets:x:2902:saturn
```

```
[root@ip-172-31-43-182 centos]# cat /etc/group | grep -E "comets|planets"
comets:x:2901:haley
planets:x:2902:saturn
```
