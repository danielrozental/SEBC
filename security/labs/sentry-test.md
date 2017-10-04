# Sentry Test

```
[root@ip-172-31-11-253 centos]# sudo su danielrozental
[danielrozental@ip-172-31-11-253 centos]$ kinit
Password for danielrozental@DANIEL.COM:
[danielrozental@ip-172-31-11-253 centos]$ beeline
Beeline version 1.1.0-cdh5.9.3 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-11-253.us-east-2.compute.internal@DANIEL.COM
scan complete in 2ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-11-253.us-east-2.compute.internal@DANIEL.COM
Connected to: Apache Hive (version 1.1.0-cdh5.9.3)
Driver: Hive JDBC (version 1.1.0-cdh5.9.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20171004171313_7a43ac8d-51aa-403b-a6c2-814a6be32a54): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171004171313_7a43ac8d-51aa-403b-a6c2-814a6be32a54); Time taken: 0.591 seconds
INFO  : Executing command(queryId=hive_20171004171313_7a43ac8d-51aa-403b-a6c2-814a6be32a54): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171004171313_7a43ac8d-51aa-403b-a6c2-814a6be32a54); Time taken: 0.223 seconds
INFO  : OK
+-----------+--+
| tab_name  |
+-----------+--+
+-----------+--+
No rows selected (2.116 seconds)
0: jdbc:hive2://localhost:10000/default>
```

```
0: jdbc:hive2://localhost:10000/default> CREATE ROLE sentry_admin;
INFO  : Compiling command(queryId=hive_20171004171515_08b463d2-766c-4383-89ca-0c1a43d7900d): CREATE ROLE sentry_admin
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171004171515_08b463d2-766c-4383-89ca-0c1a43d7900d); Time taken: 0.059 seconds
INFO  : Executing command(queryId=hive_20171004171515_08b463d2-766c-4383-89ca-0c1a43d7900d): CREATE ROLE sentry_admin
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171004171515_08b463d2-766c-4383-89ca-0c1a43d7900d); Time taken: 0.445 seconds
INFO  : OK
No rows affected (0.555 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT ALL ON SERVER server1 TO ROLE sentry_admin;
INFO  : Compiling command(queryId=hive_20171004171515_dda2814d-10e2-4c1f-8d45-2d4439b86b47): GRANT ALL ON SERVER server1 TO ROLE sentry_admin
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171004171515_dda2814d-10e2-4c1f-8d45-2d4439b86b47); Time taken: 0.092 seconds
INFO  : Executing command(queryId=hive_20171004171515_dda2814d-10e2-4c1f-8d45-2d4439b86b47): GRANT ALL ON SERVER server1 TO ROLE sentry_admin
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171004171515_dda2814d-10e2-4c1f-8d45-2d4439b86b47); Time taken: 0.07 seconds
INFO  : OK
No rows affected (0.173 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT ROLE sentry_admin TO GROUP danielrozental
. . . . . . . . . . . . . . . . . . . .> ;
INFO  : Compiling command(queryId=hive_20171004171515_d68c5e65-c258-4a82-845e-9cccc5dd5599): GRANT ROLE sentry_admin TO GROUP danielrozental
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171004171515_d68c5e65-c258-4a82-845e-9cccc5dd5599); Time taken: 0.059 seconds
INFO  : Executing command(queryId=hive_20171004171515_d68c5e65-c258-4a82-845e-9cccc5dd5599): GRANT ROLE sentry_admin TO GROUP danielrozental
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171004171515_d68c5e65-c258-4a82-845e-9cccc5dd5599); Time taken: 0.063 seconds
INFO  : OK
No rows affected (0.134 seconds)
0: jdbc:hive2://localhost:10000/default> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20171004171515_155250f5-afcf-4c23-887e-f5c7972a9061): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171004171515_155250f5-afcf-4c23-887e-f5c7972a9061); Time taken: 0.053 seconds
INFO  : Executing command(queryId=hive_20171004171515_155250f5-afcf-4c23-887e-f5c7972a9061): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171004171515_155250f5-afcf-4c23-887e-f5c7972a9061); Time taken: 0.136 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.3 seconds)

```


# Create additional test users

```
[root@ip-172-31-11-253 centos]# sudo groupadd selector
[root@ip-172-31-11-253 centos]# sudo groupadd inserters
[root@ip-172-31-11-253 centos]# sudo useradd -u 1100 -g selector george
[root@ip-172-31-11-253 centos]# sudo useradd -u 1200 -g inserters ferdinand
[root@ip-172-31-11-253 centos]# kadmin.local
Authenticating as principal danielrozental/admin@DANIEL.COM with password.
kadmin.local:  add_principal george
WARNING: no policy specified for george@DANIEL.COM; defaulting to no policy
Enter password for principal "george@DANIEL.COM":
Re-enter password for principal "george@DANIEL.COM":
Principal "george@DANIEL.COM" created.
kadmin.local:  add_principal ferdinand
WARNING: no policy specified for ferdinand@DANIEL.COM; defaulting to no policy
Enter password for principal "ferdinand@DANIEL.COM":
Re-enter password for principal "ferdinand@DANIEL.COM":
Principal "ferdinand@DANIEL.COM" created.
```

```
0: jdbc:hive2://localhost:10000/default> CREATE ROLE writes;
INFO  : Compiling command(queryId=hive_20171004172929_c74f6474-5aae-468e-a441-b869f6bd6cb1): CREATE ROLE writes
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171004172929_c74f6474-5aae-468e-a441-b869f6bd6cb1); Time taken: 0.049 seconds
INFO  : Executing command(queryId=hive_20171004172929_c74f6474-5aae-468e-a441-b869f6bd6cb1): CREATE ROLE writes
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171004172929_c74f6474-5aae-468e-a441-b869f6bd6cb1); Time taken: 0.02 seconds
INFO  : OK
No rows affected (0.08 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT SELECT ON DATABASE default TO ROLE reads;
INFO  : Compiling command(queryId=hive_20171004172929_dac80d31-86b2-49a6-a8ee-6c796815a161): GRANT SELECT ON DATABASE default TO ROLE reads
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171004172929_dac80d31-86b2-49a6-a8ee-6c796815a161); Time taken: 0.058 seconds
INFO  : Executing command(queryId=hive_20171004172929_dac80d31-86b2-49a6-a8ee-6c796815a161): GRANT SELECT ON DATABASE default TO ROLE reads
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171004172929_dac80d31-86b2-49a6-a8ee-6c796815a161); Time taken: 0.028 seconds
INFO  : OK
No rows affected (0.098 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT ROLE reads TO GROUP selector;
INFO  : Compiling command(queryId=hive_20171004172929_c94cf037-293f-4827-9207-b9147c263f92): GRANT ROLE reads TO GROUP selector
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171004172929_c94cf037-293f-4827-9207-b9147c263f92); Time taken: 0.048 seconds
INFO  : Executing command(queryId=hive_20171004172929_c94cf037-293f-4827-9207-b9147c263f92): GRANT ROLE reads TO GROUP selector
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171004172929_c94cf037-293f-4827-9207-b9147c263f92); Time taken: 0.023 seconds
INFO  : OK
No rows affected (0.082 seconds)
0: jdbc:hive2://localhost:10000/default> REVOKE ALL ON DATABASE default FROM ROLE writes;
INFO  : Compiling command(queryId=hive_20171004172929_9f0d2c83-7b3e-42f9-8ca4-b7ce6720d200): REVOKE ALL ON DATABASE default FROM ROLE writes
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171004172929_9f0d2c83-7b3e-42f9-8ca4-b7ce6720d200); Time taken: 0.05 seconds
INFO  : Executing command(queryId=hive_20171004172929_9f0d2c83-7b3e-42f9-8ca4-b7ce6720d200): REVOKE ALL ON DATABASE default FROM ROLE writes
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171004172929_9f0d2c83-7b3e-42f9-8ca4-b7ce6720d200); Time taken: 0.071 seconds
INFO  : OK
No rows affected (0.131 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT SELECT ON default.sample_07 TO ROLE writes;
INFO  : Compiling command(queryId=hive_20171004172929_0e119028-3c6b-431e-a5db-f51ef3b184e1): GRANT SELECT ON default.sample_07 TO ROLE writes
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171004172929_0e119028-3c6b-431e-a5db-f51ef3b184e1); Time taken: 0.05 seconds
INFO  : Executing command(queryId=hive_20171004172929_0e119028-3c6b-431e-a5db-f51ef3b184e1): GRANT SELECT ON default.sample_07 TO ROLE writes
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171004172929_0e119028-3c6b-431e-a5db-f51ef3b184e1); Time taken: 0.027 seconds
INFO  : OK
No rows affected (0.089 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT ROLE writes TO GROUP inserters;
INFO  : Compiling command(queryId=hive_20171004172929_5a604b0f-d9c1-4b30-af6b-c1003fd54312): GRANT ROLE writes TO GROUP inserters
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171004172929_5a604b0f-d9c1-4b30-af6b-c1003fd54312); Time taken: 0.05 seconds
INFO  : Executing command(queryId=hive_20171004172929_5a604b0f-d9c1-4b30-af6b-c1003fd54312): GRANT ROLE writes TO GROUP inserters
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171004172929_5a604b0f-d9c1-4b30-af6b-c1003fd54312); Time taken: 0.023 seconds
INFO  : OK
No rows affected (0.083 seconds)
```

# kinit as george, then login to beeline

```
[root@ip-172-31-11-253 centos]# sudo su george
[george@ip-172-31-11-253 centos]$ beeline
Beeline version 1.1.0-cdh5.9.3 by Apache Hive
beeline> [george@ip-172-31-11-253 centos]$ kinit
Password for george@DANIEL.COM:
[george@ip-172-31-11-253 centos]$ beeline
Beeline version 1.1.0-cdh5.9.3 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-11-253.us-east-2.compute.internal@DANIEL.COM
scan complete in 1ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-11-253.us-east-2.compute.internal@DANIEL.COM
Connected to: Apache Hive (version 1.1.0-cdh5.9.3)
Driver: Hive JDBC (version 1.1.0-cdh5.9.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20171004173333_b70c47f9-7e34-425d-84a5-9faa2aa2d526): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171004173333_b70c47f9-7e34-425d-84a5-9faa2aa2d526); Time taken: 0.057 seconds
INFO  : Executing command(queryId=hive_20171004173333_b70c47f9-7e34-425d-84a5-9faa2aa2d526): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171004173333_b70c47f9-7e34-425d-84a5-9faa2aa2d526); Time taken: 0.116 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.277 seconds)
```

```
[root@ip-172-31-11-253 centos]# sudo su ferdinand
[ferdinand@ip-172-31-11-253 centos]$ kinit
Password for ferdinand@DANIEL.COM:
[ferdinand@ip-172-31-11-253 centos]$ beeline
Beeline version 1.1.0-cdh5.9.3 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-11-253.us-east-2.compute.internal@DANIEL.COM
scan complete in 1ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-11-253.us-east-2.compute.internal@DANIEL.COM
Connected to: Apache Hive (version 1.1.0-cdh5.9.3)
Driver: Hive JDBC (version 1.1.0-cdh5.9.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20171004173434_c65208df-6be2-454c-82bc-963d0db9bcd5): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171004173434_c65208df-6be2-454c-82bc-963d0db9bcd5); Time taken: 0.058 seconds
INFO  : Executing command(queryId=hive_20171004173434_c65208df-6be2-454c-82bc-963d0db9bcd5): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171004173434_c65208df-6be2-454c-82bc-963d0db9bcd5); Time taken: 0.111 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| sample_07  |
+------------+--+
1 row selected (0.27 seconds)
```