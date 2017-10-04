[root@ip-172-31-11-253 centos]# kadmin.local
Authenticating as principal root/admin@DANIEL.COM with password.
kadmin.local:  addprinc danielrozental@DANIEL.COM
WARNING: no policy specified for danielrozental@DANIEL.COM; defaulting to no policy
Enter password for principal "danielrozental@DANIEL.COM":
Re-enter password for principal "danielrozental@DANIEL.COM":
Principal "danielrozental@DANIEL.COM" created.

[root@ip-172-31-11-253 centos]# kinit danielrozental
Password for danielrozental@DANIEL.COM:
[root@ip-172-31-11-253 centos]#
