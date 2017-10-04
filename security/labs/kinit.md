[root@ip-172-31-11-253 centos]# kadmin.local
Authenticating as principal root/admin@DANIEL.COM with password.
kadmin.local:  addprinc danielrozental@DANIEL.COM
WARNING: no policy specified for danielrozental@DANIEL.COM; defaulting to no policy
Enter password for principal "danielrozental@DANIEL.COM":
Re-enter password for principal "danielrozental@DANIEL.COM":
Principal "danielrozental@DANIEL.COM" created.

[root@ip-172-31-11-253 centos]# sudo su danielrozental
[danielrozental@ip-172-31-11-253 centos]$ kinit
Password for danielrozental@DANIEL.COM:
[danielrozental@ip-172-31-11-253 centos]$ klist
Ticket cache: FILE:/tmp/krb5cc_1001
Default principal: danielrozental@DANIEL.COM

Valid starting       Expires              Service principal
10/04/2017 15:25:23  10/05/2017 15:25:23  krbtgt/DANIEL.COM@DANIEL.COM
        renew until 10/11/2017 15:25:23
