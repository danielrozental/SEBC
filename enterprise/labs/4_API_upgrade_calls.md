```
[root@ip-172-31-11-253 yum.repos.d]# curl -X GET -u danielrozental:cloudera 'http://localhost:7180/api/version'
v17

[root@ip-172-31-11-253 yum.repos.d]# curl -X GET -u danielrozental:cloudera 'http://localhost:7180/api/v17/cm/version'
{
  "version" : "5.12.1",
  "buildUser" : "jenkins",
  "buildTimestamp" : "20170818-0807",
  "gitHash" : "9bdee611802535491d400e03c98ef694a2c77d0a",
  "snapshot" : false
}

[root@ip-172-31-11-253 yum.repos.d]# curl -X GET -u danielrozental:cloudera 'http://localhost:7180/api/v17/users'
{
  "items" : [ {
    "name" : "admin",
    "roles" : [ "ROLE_ADMIN" ]
  }, {
    "name" : "danielrozental",
    "roles" : [ "ROLE_ADMIN" ]
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ]
  } ]
}

[root@ip-172-31-11-253 yum.repos.d]# curl -X GET -u danielrozental:cloudera 'http://localhost:7180/api/v17/cm/scmDbInfo'
{
  "scmDbType" : "MYSQL",
  "embeddedDbUsed" : false
}


```