[centos@ip-172-31-11-253 ~]$ curl -X POST -u danielrozental:cloudera 'http://localhost:7180/api/v1/clusters/danielrozental/services/hive/commands/stop'
{
  "id" : 1457,
  "name" : "Stop",
  "startTime" : "2017-10-05T14:03:20.615Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}

[centos@ip-172-31-11-253 ~]$ curl -X POST -u danielrozental:cloudera 'http://localhost:7180/api/v1/clusters/danielrozental/services/hive/commands/start'
{
  "id" : 1465,
  "name" : "Start",
  "startTime" : "2017-10-05T14:03:56.414Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}

[centos@ip-172-31-11-253 ~]$ curl -X GET -u danielrozental:cloudera 'http://localhost:7180/api/v14/clusters/danielrozental/services/hive'
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://ip-172-31-11-253.us-east-2.compute.internal:7180/cmf/serviceRedirect/hive",
  "roleInstancesUrl" : "http://ip-172-31-11-253.us-east-2.compute.internal:7180/cmf/serviceRedirect/hive/instances",
  "serviceState" : "STARTED",
  "healthSummary" : "GOOD",
  "healthChecks" : [ {
    "name" : "HIVE_HIVEMETASTORES_HEALTHY",
    "summary" : "GOOD",
    "suppressed" : false
  }, {
    "name" : "HIVE_HIVESERVER2S_HEALTHY",
    "summary" : "GOOD",
    "suppressed" : false
  }, {
    "name" : "HIVE_WEBHCATS_HEALTHY",
    "summary" : "GOOD",
    "suppressed" : false
  } ],
  "configStalenessStatus" : "FRESH",
  "clientConfigStalenessStatus" : "FRESH",
  "maintenanceMode" : false,
  "maintenanceOwners" : [ ],
  "displayName" : "Hive",
  "entityStatus" : "GOOD_HEALTH"
}

