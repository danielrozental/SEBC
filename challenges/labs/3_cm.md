```
[hdfs@ip-172-31-45-212 yum.repos.d]$ hdfs dfs -ls /user
Found 7 items
drwxr-xr-x   - haley  comets           0 2017-10-06 14:10 /user/haley
drwxrwxrwx   - mapred hadoop           0 2017-10-06 14:04 /user/history
drwxrwxr-t   - hive   hive             0 2017-10-06 14:05 /user/hive
drwxrwxr-x   - hue    hue              0 2017-10-06 14:05 /user/hue
drwxrwxr-x   - oozie  oozie            0 2017-10-06 14:05 /user/oozie
drwxr-xr-x   - saturn planets          0 2017-10-06 14:10 /user/saturn
drwxr-x--x   - spark  spark            0 2017-10-06 14:04 /user/spark
```

curl -X GET -u admin:admin 'http://localhost:7180/api/v14/hosts'

```
[hdfs@ip-172-31-45-212 tmp]$ curl -X GET -u admin:admin 'http://localhost:7180/api/v14/hosts'
{
  "items" : [ {
    "hostId" : "929fa41a-4a76-48ab-b0f1-16647516683a",
    "ipAddress" : "172.31.33.183",
    "hostname" : "ip-172-31-33-183.us-east-2.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-45-212.us-east-2.compute.internal:7180/cmf/hostRedirect/929fa41a-4a76-48ab-b0f1-16647516683a",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 8,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 33299820544
  }, {
    "hostId" : "402e0486-6752-451b-960f-2efaf671a4ef",
    "ipAddress" : "172.31.35.178",
    "hostname" : "ip-172-31-35-178.us-east-2.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-45-212.us-east-2.compute.internal:7180/cmf/hostRedirect/402e0486-6752-451b-960f-2efaf671a4ef",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 8,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 33299820544
  }, {
    "hostId" : "c458e921-45fa-498a-bbd4-dca3bdfd83eb",
    "ipAddress" : "172.31.35.215",
    "hostname" : "ip-172-31-35-215.us-east-2.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-45-212.us-east-2.compute.internal:7180/cmf/hostRedirect/c458e921-45fa-498a-bbd4-dca3bdfd83eb",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 8,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 33299820544
  }, {
    "hostId" : "aed42693-6844-4e85-a126-51d74a910d77",
    "ipAddress" : "172.31.45.212",
    "hostname" : "ip-172-31-45-212.us-east-2.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-45-212.us-east-2.compute.internal:7180/cmf/hostRedirect/aed42693-6844-4e85-a126-51d74a910d77",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 8,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 33299820544
  } ]
}
```

```
[hdfs@ip-172-31-45-212 tmp]$ curl -X GET -u admin:admin 'http://localhost:7180/api/v8/clusters/danielrozental/services'
{
  "items" : [ {
    "name" : "hive",
    "type" : "HIVE",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-172-31-45-212.us-east-2.compute.internal:7180/cmf/serviceRedirect/hive",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "HIVE_HIVEMETASTORES_HEALTHY",
      "summary" : "GOOD"
    }, {
      "name" : "HIVE_HIVESERVER2S_HEALTHY",
      "summary" : "GOOD"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "Hive"
  }, {
    "name" : "zookeeper",
    "type" : "ZOOKEEPER",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-172-31-45-212.us-east-2.compute.internal:7180/cmf/serviceRedirect/zookeeper",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "ZOOKEEPER_CANARY_HEALTH",
      "summary" : "GOOD"
    }, {
      "name" : "ZOOKEEPER_SERVERS_HEALTHY",
      "summary" : "GOOD"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "ZooKeeper"
  }, {
    "name" : "hue",
    "type" : "HUE",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-172-31-45-212.us-east-2.compute.internal:7180/cmf/serviceRedirect/hue",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "HUE_HUE_SERVERS_HEALTHY",
      "summary" : "GOOD"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "Hue"
  }, {
    "name" : "oozie",
    "type" : "OOZIE",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-172-31-45-212.us-east-2.compute.internal:7180/cmf/serviceRedirect/oozie",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "OOZIE_OOZIE_SERVERS_HEALTHY",
      "summary" : "GOOD"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "Oozie"
  }, {
    "name" : "yarn",
    "type" : "YARN",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-172-31-45-212.us-east-2.compute.internal:7180/cmf/serviceRedirect/yarn",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "YARN_JOBHISTORY_HEALTH",
      "summary" : "GOOD"
    }, {
      "name" : "YARN_NODE_MANAGERS_HEALTHY",
      "summary" : "GOOD"
    }, {
      "name" : "YARN_RESOURCEMANAGERS_HEALTH",
      "summary" : "GOOD"
    }, {
      "name" : "YARN_USAGE_AGGREGATION_HEALTH",
      "summary" : "DISABLED"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "YARN (MR2 Included)"
  }, {
    "name" : "spark_on_yarn",
    "type" : "SPARK_ON_YARN",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-172-31-45-212.us-east-2.compute.internal:7180/cmf/serviceRedirect/spark_on_yarn",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "Spark"
  }, {
    "name" : "hdfs",
    "type" : "HDFS",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-172-31-45-212.us-east-2.compute.internal:7180/cmf/serviceRedirect/hdfs",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "HDFS_BLOCKS_WITH_CORRUPT_REPLICAS",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_CANARY_HEALTH",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_DATA_NODES_HEALTHY",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_FREE_SPACE_REMAINING",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_HA_NAMENODE_HEALTH",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_MISSING_BLOCKS",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_UNDER_REPLICATED_BLOCKS",
      "summary" : "GOOD"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "HDFS"
  } ]
}
```