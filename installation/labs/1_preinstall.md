# Install tools

yum -y install net-tools
yum -y install bind-utils ntp nscd
yum -y install wget

SELinux deshabilitado en esta ami
[root@ip-172-31-1-236 centos]# getenforce
Disabled


# 1. Swappiness
[root@ip-172-31-11-253 disco1]# cat /proc/sys/vm/swappiness
30

swappiness está en 30, lo cambio a 1

[root@ip-172-31-11-253 disco1]# sysctl -w vm.swappiness=1
vm.swappiness = 1
[root@ip-172-31-11-253 disco1]# cat /proc/sys/vm/swappiness                    1
1

# 2. Mount atributes

[root@ip-172-31-11-253 disco1]# cat /etc/fstab

\#
\# /etc/fstab
\# Created by anaconda on Mon Feb 22 17:08:22 2016
\#
\# Accessible filesystems, by reference, are maintained under '/dev/disk'
\# See man pages fstab(5), findfs(8), mount(8) and/or blkid(8) for more info
\#
\#UUID=ef6ba050-6cdc-416a-9380-c14304d0d206      /       xfs     defaults      0 0
\#/dev/xvdb      /mnt    auto    defaults,nofail,comment=cloudconfig     0     2
UUID=8768ad9f-5083-4c20-92e7-836fa1a22481      /disco1       ext4     defaults        0 0
/dev/xvdb      /mnt    auto    defaults,nofail,comment=cloudconfig     0       2
UUID=7c8ba329-983a-4a3d-be88-52bdc1295be0      /disco2       ext4     defaults        0 0
/dev/xvdc      /mnt    auto    defaults,nofail,comment=cloudconfig     0       2


[root@ip-172-31-6-79 centos]# cat /etc/fstab

\#
\# /etc/fstab
\# Created by anaconda on Mon Feb 22 17:08:22 2016
\#
\# Accessible filesystems, by reference, are maintained under '/dev/disk'
\# See man pages fstab(5), findfs(8), mount(8) and/or blkid(8) for more info
\#
\#UUID=ef6ba050-6cdc-416a-9380-c14304d0d206      /       xfs     defaults        0 0
\#/dev/xvdb      /mnt    auto    defaults,nofail,comment=cloudconfig     0       2
UUID=1ee72892-803c-4bc2-b828-95cc73f6437a      /disco1       ext4     defaults        0 0
/dev/xvdb      /mnt    auto    defaults,nofail,comment=cloudconfig     0       2
UUID=c37c2019-4ff0-4464-9096-05f5567d178a      /disco2       ext4     defaults        0 0
/dev/xvdc      /mnt    auto    defaults,nofail,comment=cloudconfig     0       2

[root@ip-172-31-9-51 centos]# cat /etc/fstab

\#
\# /etc/fstab
\# Created by anaconda on Mon Feb 22 17:08:22 2016
\#
\# Accessible filesystems, by reference, are maintained under '/dev/disk'
\# See man pages fstab(5), findfs(8), mount(8) and/or blkid(8) for more info
\#
\#UUID=ef6ba050-6cdc-416a-9380-c14304d0d206      /       xfs     defaults      0 0
\#/dev/xvdb      /mnt    auto    defaults,nofail,comment=cloudconfig     0     2
UUID=2f8c62c3-f677-4b26-8ea0-867c4be0811b      /disco1       ext4     defaults        0 0
/dev/xvdb      /mnt    auto    defaults,nofail,comment=cloudconfig     0       2
UUID=5545cd71-c66f-42a9-9562-b377b7754e3a      /disco2       ext4     defaults        0 0
/dev/xvdc      /mnt    auto    defaults,nofail,comment=cloudconfig     0       2

[root@ip-172-31-1-236 centos]# cat /etc/fstab

\#
\# /etc/fstab
\# Created by anaconda on Mon Feb 22 17:08:22 2016
\#
\# Accessible filesystems, by reference, are maintained under '/dev/disk'
\# See man pages fstab(5), findfs(8), mount(8) and/or blkid(8) for more info
\#
\#UUID=ef6ba050-6cdc-416a-9380-c14304d0d206      /       xfs     defaults        0 0
\#/dev/xvdb      /mnt    auto    defaults,nofail,comment=cloudconfig     0       2
UUID=5d179de4-8726-4582-8106-52a5daf28db1      /disco1       ext4     defaults        0 0
/dev/xvdb      /mnt    auto    defaults,nofail,comment=cloudconfig     0       2
UUID=91d69548-0773-4535-ae44-2771645dd05e      /disco2       ext4     defaults        0 0
/dev/xvdc      /mnt    auto    defaults,nofail,comment=cloudconfig     0       2


# 3. Free space
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

# 4. THP no lo hacemos

# 5. Network interface information

## Nodo 1
[root@ip-172-31-11-253 disco1]# ifconfig
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 9001
        inet 172.31.11.253  netmask 255.255.240.0  broadcast 172.31.15.255
        inet6 fe80::d2:8fff:fec3:ca04  prefixlen 64  scopeid 0x20<link>
        ether 02:d2:8f:c3:ca:04  txqueuelen 1000  (Ethernet)
        RX packets 32556  bytes 33890775 (32.3 MiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 21252  bytes 2501859 (2.3 MiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 0  (Local Loopback)
        RX packets 6  bytes 416 (416.0 B)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 6  bytes 416 (416.0 B)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

## Nodo 2
[root@ip-172-31-6-79 centos]# ifconfig
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 9001
        inet 172.31.6.79  netmask 255.255.240.0  broadcast 172.31.15.255
        inet6 fe80::40:32ff:fe48:e2b2  prefixlen 64  scopeid 0x20<link>
        ether 02:40:32:48:e2:b2  txqueuelen 1000  (Ethernet)
        RX packets 25067  bytes 33219463 (31.6 MiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 15168  bytes 1230188 (1.1 MiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 0  (Local Loopback)
        RX packets 6  bytes 416 (416.0 B)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 6  bytes 416 (416.0 B)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

## Nodo 3
[root@ip-172-31-9-51 centos]# ifconfig
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 9001
        inet 172.31.9.51  netmask 255.255.240.0  broadcast 172.31.15.255
        inet6 fe80::67:dcff:fea8:535c  prefixlen 64  scopeid 0x20<link>
        ether 02:67:dc:a8:53:5c  txqueuelen 1000  (Ethernet)
        RX packets 24433  bytes 33184120 (31.6 MiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 15173  bytes 1225860 (1.1 MiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 0  (Local Loopback)
        RX packets 6  bytes 416 (416.0 B)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 6  bytes 416 (416.0 B)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

## Nodo 4
[root@ip-172-31-1-236 centos]# ifconfig
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 9001
        inet 172.31.1.236  netmask 255.255.240.0  broadcast 172.31.15.255
        inet6 fe80::39:64ff:fed2:730a  prefixlen 64  scopeid 0x20<link>
        ether 02:39:64:d2:73:0a  txqueuelen 1000  (Ethernet)
        RX packets 24563  bytes 33160899 (31.6 MiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 15665  bytes 1187848 (1.1 MiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 0  (Local Loopback)
        RX packets 6  bytes 416 (416.0 B)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 6  bytes 416 (416.0 B)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
		
# 6. Network check

[root@ip-172-31-11-253 disco1]# nslookup 172.31.11.253
Server:         172.31.0.2
Address:        172.31.0.2#53

Non-authoritative answer:
253.11.31.172.in-addr.arpa      name = ip-172-31-11-253.us-east-2.compute.internal.

Authoritative answers can be found from:

[root@ip-172-31-11-253 disco1]# nslookup 172.31.6.79
Server:         172.31.0.2
Address:        172.31.0.2#53

Non-authoritative answer:
79.6.31.172.in-addr.arpa        name = ip-172-31-6-79.us-east-2.compute.internal.

Authoritative answers can be found from:

[root@ip-172-31-11-253 disco1]# nslookup 172.31.9.51
Server:         172.31.0.2
Address:        172.31.0.2#53

Non-authoritative answer:
51.9.31.172.in-addr.arpa        name = ip-172-31-9-51.us-east-2.compute.internal.

Authoritative answers can be found from:

[root@ip-172-31-11-253 disco1]# nslookup 172.31.1.236
Server:         172.31.0.2
Address:        172.31.0.2#53

Non-authoritative answer:
236.1.31.172.in-addr.arpa       name = ip-172-31-1-236.us-east-2.compute.internal.

Authoritative answers can be found from:

NSLOOKUP

[root@ip-172-31-11-253 disco1]# nslookup ip-172-31-11-253.us-east-2.compute.internal
Server:         172.31.0.2
Address:        172.31.0.2#53

Non-authoritative answer:
Name:   ip-172-31-11-253.us-east-2.compute.internal
Address: 172.31.11.253

[root@ip-172-31-11-253 disco1]# nslookup ip-172-31-6-79.us-east-2.compute.internal
Server:         172.31.0.2
Address:        172.31.0.2#53

Non-authoritative answer:
Name:   ip-172-31-6-79.us-east-2.compute.internal
Address: 172.31.6.79

[root@ip-172-31-11-253 disco1]# nslookup ip-172-31-9-51.us-east-2.compute.internal
Server:         172.31.0.2
Address:        172.31.0.2#53

Non-authoritative answer:
Name:   ip-172-31-9-51.us-east-2.compute.internal
Address: 172.31.9.51

[root@ip-172-31-11-253 disco1]# nslookup ip-172-31-1-236.us-east-2.compute.internal
Server:         172.31.0.2
Address:        172.31.0.2#53

Non-authoritative answer:
Name:   ip-172-31-1-236.us-east-2.compute.internal
Address: 172.31.1.236

# 6. nscd

[root@ip-172-31-11-253 disco1]# systemctl start nscd
[root@ip-172-31-11-253 disco1]# systemctl enable nscd
Created symlink from /etc/systemd/system/multi-user.target.wants/nscd.service to /usr/lib/systemd/system/nscd.service.
Created symlink from /etc/systemd/system/sockets.target.wants/nscd.socket to /usr/lib/systemd/system/nscd.socket.
[root@ip-172-31-11-253 disco1]# systemctl status nscd
● nscd.service - Name Service Cache Daemon
   Loaded: loaded (/usr/lib/systemd/system/nscd.service; enabled; vendor preset: disabled)
   Active: active (running) since Mon 2017-10-02 17:04:06 UTC; 45s ago
 Main PID: 18017 (nscd)
   CGroup: /system.slice/nscd.service
           └─18017 /usr/sbin/nscd

Oct 02 17:04:06 ip-172-31-11-253 nscd[18017]: 18017 monitoring directory `/...)
Oct 02 17:04:06 ip-172-31-11-253 nscd[18017]: 18017 monitoring file `/etc/r...)
Oct 02 17:04:06 ip-172-31-11-253 nscd[18017]: 18017 monitoring directory `/...)
Oct 02 17:04:06 ip-172-31-11-253 nscd[18017]: 18017 monitoring file `/etc/s...)
Oct 02 17:04:06 ip-172-31-11-253 nscd[18017]: 18017 monitoring directory `/...)
Oct 02 17:04:06 ip-172-31-11-253 nscd[18017]: 18017 disabled inotify-based ...y
Oct 02 17:04:06 ip-172-31-11-253 nscd[18017]: 18017 stat failed for file `/...y
Oct 02 17:04:06 ip-172-31-11-253 systemd[1]: Started Name Service Cache Daemon.
Oct 02 17:04:25 ip-172-31-11-253 nscd[18017]: 18017 checking for monitored ...y
Oct 02 17:04:29 ip-172-31-11-253 systemd[1]: Started Name Service Cache Daemon.
Hint: Some lines were ellipsized, use -l to show in full.


# 7. ntpd

https://www.cloudera.com/documentation/enterprise/5-5-x/topics/install_cdh_enable_ntp.html

[root@ip-172-31-11-253 disco1]# vi /etc/ntp.conf

[root@ip-172-31-11-253 disco1]# cat /etc/ntp.conf
\# For more information about this file, see the man pages
\# ntp.conf(5), ntp_acc(5), ntp_auth(5), ntp_clock(5), ntp_misc(5), ntp_mon(5).

driftfile /var/lib/ntp/drift

\# Permit time synchronization with our time source, but do not
\# permit the source to query or modify the service on this system.
restrict default nomodify notrap nopeer noquery

\# Permit all access over the loopback interface.  This could
\# be tightened as well, but to do so would effect some of
\# the administrative functions.
restrict 127.0.0.1
restrict ::1

\# Hosts on local network are less restricted.
\#restrict 192.168.1.0 mask 255.255.255.0 nomodify notrap

\# Use public servers from the pool.ntp.org project.
\# Please consider joining the pool (http://www.pool.ntp.org/join.html).
server 0.pool.ntp.org
server 1.pool.ntp.org
server 2.pool.ntp.org

\#broadcast 192.168.1.255 autokey        # broadcast server
\#broadcastclient                        # broadcast client
\#broadcast 224.0.1.1 autokey            # multicast server
\#multicastclient 224.0.1.1              # multicast client
\#manycastserver 239.255.254.254         # manycast server
\#manycastclient 239.255.254.254 autokey # manycast client

\# Enable public key cryptography.
\#crypto

includefile /etc/ntp/crypto/pw

\# Key file containing the keys and key identifiers used when operating
\# with symmetric key cryptography.
keys /etc/ntp/keys

\# Specify the key identifiers which are trusted.
\#trustedkey 4 8 42

\# Specify the key identifier to use with the ntpdc utility.
\#requestkey 8

\# Specify the key identifier to use with the ntpq utility.
\#controlkey 8

\# Enable writing of statistics records.
\#statistics clockstats cryptostats loopstats peerstats

\# Disable the monitoring facility to prevent amplification attacks using ntpdc
\# monlist command when default restrict does not include the noquery flag. See
\# CVE-2013-5211 for more details.
\# Note: Monitoring will not be disabled with the limited restriction flag.
disable monitor



[root@ip-172-31-11-253 disco1]# systemctl disable chronyd
Removed symlink /etc/systemd/system/multi-user.target.wants/chronyd.service.
[root@ip-172-31-11-253 disco1]# chkconfig ntpd on
Note: Forwarding request to 'systemctl enable ntpd.service'.
Created symlink from /etc/systemd/system/multi-user.target.wants/ntpd.service to /usr/lib/systemd/system/ntpd.service.
[root@ip-172-31-11-253 disco1]# service ntpd start
Redirecting to /bin/systemctl start  ntpd.service

[root@ip-172-31-11-253 disco1]# systemctl status ntpd
● ntpd.service - Network Time Service
   Loaded: loaded (/usr/lib/systemd/system/ntpd.service; enabled; vendor preset: disabled)
   Active: active (running) since Mon 2017-10-02 17:18:05 UTC; 4min 46s ago
  Process: 18149 ExecStart=/usr/sbin/ntpd -u ntp:ntp $OPTIONS (code=exited, status=0/SUCCESS)
 Main PID: 18150 (ntpd)
   CGroup: /system.slice/ntpd.service
           └─18150 /usr/sbin/ntpd -u ntp:ntp -g

Oct 02 17:18:05 ip-172-31-11-253 ntpd[18150]: Listen normally on 2 lo 127.0...3
Oct 02 17:18:05 ip-172-31-11-253 ntpd[18150]: Listen normally on 3 eth0 172...3
Oct 02 17:18:05 ip-172-31-11-253 ntpd[18150]: Listen normally on 4 lo ::1 U...3
Oct 02 17:18:05 ip-172-31-11-253 ntpd[18150]: Listen normally on 5 eth0 fe8...3
Oct 02 17:18:05 ip-172-31-11-253 ntpd[18150]: Listening on routing socket o...s
Oct 02 17:18:05 ip-172-31-11-253 systemd[1]: Started Network Time Service.
Oct 02 17:18:05 ip-172-31-11-253 ntpd[18150]: 0.0.0.0 c016 06 restart
Oct 02 17:18:05 ip-172-31-11-253 ntpd[18150]: 0.0.0.0 c012 02 freq_set kern...M
Oct 02 17:18:05 ip-172-31-11-253 ntpd[18150]: 0.0.0.0 c011 01 freq_not_set
Oct 02 17:21:23 ip-172-31-11-253 ntpd[18150]: 0.0.0.0 c614 04 freq_mode
Hint: Some lines were ellipsized, use -l to show in full.
