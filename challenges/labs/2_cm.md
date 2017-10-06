```
[root@ip-172-31-45-212 yum.repos.d]# ls /etc/yum.repos.d
CentOS-Base.repo       CentOS-fasttrack.repo  CentOS-Vault.repo
CentOS-CR.repo         CentOS-Media.repo      cloudera-manager.repo
CentOS-Debuginfo.repo  CentOS-Sources.repo
```

```
[root@ip-172-31-45-212 yum.repos.d]# sudo /usr/share/cmf/schema/scm_prepare_database.sh -h ip-172-31-35-178.us-east-2.compute.internal mysql scm scm
Enter SCM password:
JAVA_HOME=/usr/java/jdk1.7.0_67-cloudera
Verifying that we can write to /etc/cloudera-scm-server
Creating SCM configuration file in /etc/cloudera-scm-server
Executing:  /usr/java/jdk1.7.0_67-cloudera/bin/java -cp /usr/share/java/mysql-connector-java.jar:/usr/share/java/oracle-connector-java.jar:/usr/share/cmf/schema/../lib/* com.cloudera.enterprise.dbutil.DbCommandExecutor /etc/cloudera-scm-server/db.properties com.cloudera.cmf.db.
[                          main] DbCommandExecutor              INFO  Successfully connected to database.
All done, your SCM database is configured correctly!
```
