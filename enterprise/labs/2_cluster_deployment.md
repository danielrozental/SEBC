curl -X GET -u "danielrozental:cloudera" -i http://ip-172-31-11-253:7180/api/v2/cm/deployment

```
[centos@ip-172-31-11-253 ~]$ curl -X GET -u "danielrozental:cloudera" -i http://ip-172-31-11-253:7180/api/v2/cm/deployment
HTTP/1.1 200 OK
Expires: Thu, 01-Jan-1970 00:00:00 GMT
Set-Cookie: CLOUDERA_MANAGER_SESSIONID=19s9z6y6qdhwqsjjmndd5sve6;Path=/;HttpOnly
Content-Type: application/json
Date: Thu, 05 Oct 2017 13:50:58 GMT
Transfer-Encoding: chunked
Server: Jetty(6.1.26.cloudera.4)

{
  "timestamp" : "2017-10-05T13:50:58.740Z",
  "clusters" : [ {
    "name" : "danielrozental",
    "version" : "CDH5",
    "services" : [ {
      "name" : "hive",
      "type" : "HIVE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "HIVEMETASTORE",
          "items" : [ {
            "name" : "hive_metastore_java_heapsize",
            "value" : "6446645248"
          }, {
            "name" : "hive_metastore_server_max_message_size",
            "value" : "644664524"
          } ]
        }, {
          "roleType" : "HIVESERVER2",
          "items" : [ {
            "name" : "hiveserver2_enable_impersonation",
            "value" : "false"
          }, {
            "name" : "hiveserver2_spark_driver_memory",
            "value" : "966367641"
          }, {
            "name" : "hiveserver2_spark_executor_cores",
            "value" : "4"
          }, {
            "name" : "hiveserver2_spark_executor_memory",
            "value" : "3561593241"
          }, {
            "name" : "hiveserver2_spark_yarn_driver_memory_overhead",
            "value" : "102"
          }, {
            "name" : "hiveserver2_spark_yarn_executor_memory_overhead",
            "value" : "599"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_metastore_database_host",
          "value" : "ip-172-31-11-253.us-east-2.compute.internal"
        }, {
          "name" : "hive_metastore_database_password",
          "value" : "hive_password"
        }, {
          "name" : "hive_proxy_user_groups_list",
          "value" : "hive,hue"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "sentry_service",
          "value" : "sentry"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hive-GATEWAY-e89a0a513c5a4bb9da727278797b5cfe",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-01b1d81668be33301"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-HIVEMETASTORE-6c941f8216895674eff6a6c9a518f1eb",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "i-01e5c13137c814b8c"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "clowl1oprf2fqzp5vvsvxz32h"
          } ]
        }
      }, {
        "name" : "hive-HIVESERVER2-e89a0a513c5a4bb9da727278797b5cfe",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "i-01b1d81668be33301"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "bvavex94kzvuqyc5c7r9divp2"
          } ]
        }
      }, {
        "name" : "hive-WEBHCAT-e89a0a513c5a4bb9da727278797b5cfe",
        "type" : "WEBHCAT",
        "hostRef" : {
          "hostId" : "i-01b1d81668be33301"
        },
        "config" : {
          "items" : [ {
            "name" : "hive_webhcat_secret_key",
            "value" : "2tjhDsBdilJVG3Yva6D3YvQaK1XGC8"
          }, {
            "name" : "role_jceks_password",
            "value" : "68me8fwqn3rf2xpn9pi5ztgbz"
          } ]
        }
      } ],
      "displayName" : "Hive"
    }, {
      "name" : "zookeeper",
      "type" : "ZOOKEEPER",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ {
          "name" : "enableSecurity",
          "value" : "true"
        } ]
      },
      "roles" : [ {
        "name" : "zookeeper-SERVER-6c941f8216895674eff6a6c9a518f1eb",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-01e5c13137c814b8c"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6ufjyak4x0v7bczi9rvvwyhh6"
          }, {
            "name" : "serverId",
            "value" : "2"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-aacae6e08984cce5f9a17b53f92183f5",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-0fe9023c0906c8ab1"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4w00dvg7xm28rnm5or4zzdllh"
          }, {
            "name" : "serverId",
            "value" : "1"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-c46b0fbc2b511e94bc7d9c40d88df13d",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-0b1f215533a57d0eb"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "268us8pozb3ww34muc0vou5yb"
          }, {
            "name" : "serverId",
            "value" : "3"
          } ]
        }
      } ],
      "displayName" : "ZooKeeper"
    }, {
      "name" : "hue",
      "type" : "HUE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "HUE_LOAD_BALANCER",
          "items" : [ {
            "name" : "listen",
            "value" : "18889"
          } ]
        }, {
          "roleType" : "HUE_SERVER",
          "items" : [ {
            "name" : "hue_http_port",
            "value" : "18888"
          }, {
            "name" : "hue_server_bind_wildcard",
            "value" : "true"
          } ]
        } ],
        "items" : [ {
          "name" : "database_host",
          "value" : "ip-172-31-11-253.us-east-2.compute.internal"
        }, {
          "name" : "database_password",
          "value" : "secretpassword"
        }, {
          "name" : "database_type",
          "value" : "mysql"
        }, {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "hue_webhdfs",
          "value" : "hdfs-HTTPFS-e89a0a513c5a4bb9da727278797b5cfe"
        }, {
          "name" : "oozie_service",
          "value" : "oozie"
        }, {
          "name" : "sentry_service",
          "value" : "sentry"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hue-HUE_SERVER-e89a0a513c5a4bb9da727278797b5cfe",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "i-01b1d81668be33301"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7bmwgg8m1llie570q3erc8ksk"
          }, {
            "name" : "secret_key",
            "value" : "yE38rXHBJUVDJU1gAv45RaPoJSihbI"
          } ]
        }
      }, {
        "name" : "hue-KT_RENEWER-e89a0a513c5a4bb9da727278797b5cfe",
        "type" : "KT_RENEWER",
        "hostRef" : {
          "hostId" : "i-01b1d81668be33301"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "90vof5zv3qa53cvdfk077ms8d"
          } ]
        }
      } ],
      "displayName" : "Hue"
    }, {
      "name" : "oozie",
      "type" : "OOZIE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "OOZIE_SERVER",
          "items" : [ {
            "name" : "oozie_database_host",
            "value" : "ip-172-31-11-253.us-east-2.compute.internal"
          }, {
            "name" : "oozie_database_password",
            "value" : "oozie"
          }, {
            "name" : "oozie_database_type",
            "value" : "mysql"
          }, {
            "name" : "oozie_database_user",
            "value" : "oozie"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "oozie-OOZIE_SERVER-e89a0a513c5a4bb9da727278797b5cfe",
        "type" : "OOZIE_SERVER",
        "hostRef" : {
          "hostId" : "i-01b1d81668be33301"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "am850zzxewqktj57d63wk4i76"
          } ]
        }
      } ],
      "displayName" : "Oozie"
    }, {
      "name" : "yarn",
      "type" : "YARN",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "mapred_reduce_tasks",
            "value" : "12"
          }, {
            "name" : "mapred_submit_replication",
            "value" : "1"
          } ]
        }, {
          "roleType" : "NODEMANAGER",
          "items" : [ {
            "name" : "rm_cpu_shares",
            "value" : "1600"
          }, {
            "name" : "rm_io_weight",
            "value" : "800"
          }, {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100"
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/disco1/yarn/nm,/disco2/yarn/nm"
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/disco1/yarn/container-logs,/disco2/yarn/container-logs"
          }, {
            "name" : "yarn_nodemanager_resource_cpu_vcores",
            "value" : "6"
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "9661"
          } ]
        }, {
          "roleType" : "RESOURCEMANAGER",
          "items" : [ {
            "name" : "yarn_scheduler_maximum_allocation_mb",
            "value" : "15319"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_vcores",
            "value" : "6"
          } ]
        } ],
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "80"
        }, {
          "name" : "yarn_service_cgroups",
          "value" : "false"
        }, {
          "name" : "yarn_service_lce_always",
          "value" : "false"
        }, {
          "name" : "zk_authorization_secret_key",
          "value" : "hSA3GeGjaYk6fZkufl77RG8JtzqgVG"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "yarn-JOBHISTORY-6c941f8216895674eff6a6c9a518f1eb",
        "type" : "JOBHISTORY",
        "hostRef" : {
          "hostId" : "i-01e5c13137c814b8c"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9waef3r3jrigiaa1m6uroc814"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-6c941f8216895674eff6a6c9a518f1eb",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-01e5c13137c814b8c"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4nx9wiezo71qsagtfrwibtrc1"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-aacae6e08984cce5f9a17b53f92183f5",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-0fe9023c0906c8ab1"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "8k75j8rr77nvtznyepj8k52k1"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-c46b0fbc2b511e94bc7d9c40d88df13d",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-0b1f215533a57d0eb"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7v4oecx32jld85icfaa8y81ps"
          } ]
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-aacae6e08984cce5f9a17b53f92183f5",
        "type" : "RESOURCEMANAGER",
        "hostRef" : {
          "hostId" : "i-0fe9023c0906c8ab1"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_id",
            "value" : "91"
          }, {
            "name" : "role_jceks_password",
            "value" : "1a17bhct61psvu0kctm5mjeam"
          } ]
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-c46b0fbc2b511e94bc7d9c40d88df13d",
        "type" : "RESOURCEMANAGER",
        "hostRef" : {
          "hostId" : "i-0b1f215533a57d0eb"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_id",
            "value" : "76"
          }, {
            "name" : "role_jceks_password",
            "value" : "68d2csuwlyagphuki8daalsgx"
          } ]
        }
      } ],
      "displayName" : "YARN (MR2 Included)"
    }, {
      "name" : "hdfs",
      "type" : "HDFS",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "DATANODE",
          "items" : [ {
            "name" : "datanode_java_heapsize",
            "value" : "1073741824"
          }, {
            "name" : "dfs_data_dir_list",
            "value" : "/disco1/dfs/dn,/disco2/dfs/dn"
          }, {
            "name" : "dfs_datanode_bind_wildcard",
            "value" : "true"
          }, {
            "name" : "dfs_datanode_data_dir_perm",
            "value" : "700"
          }, {
            "name" : "dfs_datanode_failed_volumes_tolerated",
            "value" : "1"
          }, {
            "name" : "dfs_datanode_http_port",
            "value" : "1006"
          }, {
            "name" : "dfs_datanode_max_locked_memory",
            "value" : "4294967296"
          }, {
            "name" : "dfs_datanode_port",
            "value" : "1004"
          }, {
            "name" : "rm_cpu_shares",
            "value" : "400"
          }, {
            "name" : "rm_io_weight",
            "value" : "200"
          } ]
        }, {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "dfs_client_use_trash",
            "value" : "true"
          } ]
        }, {
          "roleType" : "JOURNALNODE",
          "items" : [ {
            "name" : "dfs_journalnode_edits_dir",
            "value" : "/disco1/dfs/jn"
          }, {
            "name" : "journalnode_bind_wildcard",
            "value" : "true"
          } ]
        }, {
          "roleType" : "NAMENODE",
          "items" : [ {
            "name" : "dfs_name_dir_list",
            "value" : "/disco1/dfs/nn,/disco2/dfs/nn"
          }, {
            "name" : "dfs_namenode_servicerpc_address",
            "value" : "8022"
          }, {
            "name" : "namenode_bind_wildcard",
            "value" : "true"
          } ]
        }, {
          "roleType" : "SECONDARYNAMENODE",
          "items" : [ {
            "name" : "fs_checkpoint_dir_list",
            "value" : "/disco1/dfs/snn"
          }, {
            "name" : "secondary_namenode_bind_wildcard",
            "value" : "true"
          } ]
        } ],
        "items" : [ {
          "name" : "dfs_client_use_datanode_hostname",
          "value" : "true"
        }, {
          "name" : "dfs_encrypt_data_transfer_algorithm",
          "value" : "AES/CTR/NoPadding"
        }, {
          "name" : "dfs_ha_fencing_cloudera_manager_secret_key",
          "value" : "voeb3gUXl7lXMagwVMVKjTJc1j4zjb"
        }, {
          "name" : "dfs_ha_fencing_methods",
          "value" : "shell(true)"
        }, {
          "name" : "dfs_namenode_acls_enabled",
          "value" : "true"
        }, {
          "name" : "fc_authorization_secret_key",
          "value" : "jpfIta992vGPZL0bdIdVMy73t64LUL"
        }, {
          "name" : "hadoop_secure_web_ui",
          "value" : "true"
        }, {
          "name" : "hadoop_security_authentication",
          "value" : "kerberos"
        }, {
          "name" : "hadoop_security_authorization",
          "value" : "true"
        }, {
          "name" : "hdfs_sentry_sync_enable",
          "value" : "true"
        }, {
          "name" : "http_auth_signature_secret",
          "value" : "SemMrjdNKqRSg2QAOwwOmpyvjyYKde"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "20"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hdfs-BALANCER-aacae6e08984cce5f9a17b53f92183f5",
        "type" : "BALANCER",
        "hostRef" : {
          "hostId" : "i-0fe9023c0906c8ab1"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-DATANODE-6c941f8216895674eff6a6c9a518f1eb",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-01e5c13137c814b8c"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9yhgewct2k7uvyufo5p2d0mg8"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-aacae6e08984cce5f9a17b53f92183f5",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-0fe9023c0906c8ab1"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "ctb22mhyvpoj3rj6o7e7r5unc"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-c46b0fbc2b511e94bc7d9c40d88df13d",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-0b1f215533a57d0eb"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "cewc2bhg0wfwaakws4pmov6x1"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-6c941f8216895674eff6a6c9a518f1eb",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "i-01e5c13137c814b8c"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "cpu5te5cbp32svych61kwpivi"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-aacae6e08984cce5f9a17b53f92183f5",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "i-0fe9023c0906c8ab1"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5adqyapql37tyf1casgxpfbei"
          } ]
        }
      }, {
        "name" : "hdfs-HTTPFS-e89a0a513c5a4bb9da727278797b5cfe",
        "type" : "HTTPFS",
        "hostRef" : {
          "hostId" : "i-01b1d81668be33301"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "45zfm2tl8eodqjbvu3lb0yy0n"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-6c941f8216895674eff6a6c9a518f1eb",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-01e5c13137c814b8c"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "bkh9l1j0ju4w2d75ha2fhp8m4"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-aacae6e08984cce5f9a17b53f92183f5",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-0fe9023c0906c8ab1"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "l90b6pm7w7xgsfxifq3tgrun"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-c46b0fbc2b511e94bc7d9c40d88df13d",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-0b1f215533a57d0eb"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "aul59qvh4uga2dmj9rpbgl5xz"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-6c941f8216895674eff6a6c9a518f1eb",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "i-01e5c13137c814b8c"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice1"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice1"
          }, {
            "name" : "namenode_id",
            "value" : "85"
          }, {
            "name" : "role_jceks_password",
            "value" : "2exq3tvasnvza1lbehqw30ul7"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-aacae6e08984cce5f9a17b53f92183f5",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "i-0fe9023c0906c8ab1"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice1"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice1"
          }, {
            "name" : "namenode_id",
            "value" : "80"
          }, {
            "name" : "role_jceks_password",
            "value" : "enmemuw4xx285f92e6i9x0803"
          } ]
        }
      } ],
      "displayName" : "HDFS"
    }, {
      "name" : "sentry",
      "type" : "SENTRY",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs"
        }, {
          "name" : "sentry_server_database_host",
          "value" : "ip-172-31-11-253"
        }, {
          "name" : "sentry_server_database_password",
          "value" : "sentry_password"
        }, {
          "name" : "sentry_service_admin_group",
          "value" : "hive,impala,hue,solr,kafka,danielrozental"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "sentry-GATEWAY-c46b0fbc2b511e94bc7d9c40d88df13d",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-0b1f215533a57d0eb"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "sentry-SENTRY_SERVER-c46b0fbc2b511e94bc7d9c40d88df13d",
        "type" : "SENTRY_SERVER",
        "hostRef" : {
          "hostId" : "i-0b1f215533a57d0eb"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "2md8fistbckmr6kdcp7bsxfh"
          } ]
        }
      } ],
      "displayName" : "Sentry"
    } ]
  } ],
  "hosts" : [ {
    "hostId" : "i-0fe9023c0906c8ab1",
    "ipAddress" : "172.31.1.236",
    "hostname" : "ip-172-31-1-236.us-east-2.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-01b1d81668be33301",
    "ipAddress" : "172.31.11.253",
    "hostname" : "ip-172-31-11-253.us-east-2.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-01e5c13137c814b8c",
    "ipAddress" : "172.31.6.79",
    "hostname" : "ip-172-31-6-79.us-east-2.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-0b1f215533a57d0eb",
    "ipAddress" : "172.31.9.51",
    "hostname" : "ip-172-31-9-51.us-east-2.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  } ],
  "users" : [ {
    "name" : "__cloudera_internal_user__7f30c0b8-bf02-4b10-961b-ed7f86755089",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "863cd0f2e2215b04bc731ab3350ab2791c683f478eaa5a5ab07b1e5576ba0fbe",
    "pwSalt" : -6244112832466499616,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-ACTIVITYMONITOR-e89a0a513c5a4bb9da727278797b5cfe",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "2790d027e2aca22621fd5526f7a9c02a244f7d2924edeec4458149988b28a3af",
    "pwSalt" : -9072971777609763075,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-EVENTSERVER-e89a0a513c5a4bb9da727278797b5cfe",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "e28990471efc631eb31c40743b74089b98c4c0a23bc58bb36960a7c45c16d3a0",
    "pwSalt" : -5131891109951725291,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-HOSTMONITOR-e89a0a513c5a4bb9da727278797b5cfe",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "b8cbddcdf21b24846f135c765c2b5b709f197822606e9695b335708c9e8336d4",
    "pwSalt" : 8859887934479989973,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-REPORTSMANAGER-e89a0a513c5a4bb9da727278797b5cfe",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "0ae6f5733cf0d9e07f52994746107e66d430d454d4681d7cba04a412c1c67954",
    "pwSalt" : 893561160682700886,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-SERVICEMONITOR-e89a0a513c5a4bb9da727278797b5cfe",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "cc2f3d033f1fe379c0602fb3808cb6d69282e3cc2be3827c0e08744f2cea6d37",
    "pwSalt" : 1102073135195012179,
    "pwLogin" : true
  }, {
    "name" : "admin",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "a7d7ef1852ba4c4b6a3a31225eb08323fe5985927753ac7c0868e85549b516ea",
    "pwSalt" : -8974741439754041383,
    "pwLogin" : true
  }, {
    "name" : "danielrozental",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "870b4164bb4dd78bdef12692c1079de14ee556a6123ef0cf64fa999b195c0bce",
    "pwSalt" : -2021891577917718899,
    "pwLogin" : true
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ],
    "pwHash" : "1e007cb851807b4a7e724fb396c238b6bbb37569efab49cd5dd081d9a664a282",
    "pwSalt" : 7665087655148033458,
    "pwLogin" : true
  } ],
  "versionInfo" : {
    "version" : "5.9.3",
    "buildUser" : "jenkins",
    "buildTimestamp" : "20170627-1506",
    "gitHash" : "23506bb4e114dd460bdac64c57a672e6be631907",
    "snapshot" : false
  },
  "managementService" : {
    "name" : "mgmt",
    "type" : "MGMT",
    "config" : {
      "roleTypeConfigs" : [ {
        "roleType" : "ACTIVITYMONITOR",
        "items" : [ {
          "name" : "firehose_database_host",
          "value" : "ip-172-31-11-253.us-east-2.compute.internal"
        }, {
          "name" : "firehose_database_name",
          "value" : "amon"
        }, {
          "name" : "firehose_database_password",
          "value" : "amon_password"
        }, {
          "name" : "firehose_database_user",
          "value" : "amon"
        } ]
      }, {
        "roleType" : "HOSTMONITOR",
        "items" : [ {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "1610612736"
        } ]
      }, {
        "roleType" : "REPORTSMANAGER",
        "items" : [ {
          "name" : "headlamp_database_host",
          "value" : "ip-172-31-11-253.us-east-2.compute.internal"
        }, {
          "name" : "headlamp_database_name",
          "value" : "rman"
        }, {
          "name" : "headlamp_database_password",
          "value" : "rman_password"
        }, {
          "name" : "headlamp_database_user",
          "value" : "rman"
        } ]
      }, {
        "roleType" : "SERVICEMONITOR",
        "items" : [ {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "1610612736"
        } ]
      } ],
      "items" : [ ]
    },
    "roles" : [ {
      "name" : "mgmt-ACTIVITYMONITOR-e89a0a513c5a4bb9da727278797b5cfe",
      "type" : "ACTIVITYMONITOR",
      "hostRef" : {
        "hostId" : "i-01b1d81668be33301"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "e4kkmibp5qacx8g6io76btoop"
        } ]
      }
    }, {
      "name" : "mgmt-ALERTPUBLISHER-e89a0a513c5a4bb9da727278797b5cfe",
      "type" : "ALERTPUBLISHER",
      "hostRef" : {
        "hostId" : "i-01b1d81668be33301"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "5n6fc3pptmrkb22plb5kxo1wu"
        } ]
      }
    }, {
      "name" : "mgmt-EVENTSERVER-e89a0a513c5a4bb9da727278797b5cfe",
      "type" : "EVENTSERVER",
      "hostRef" : {
        "hostId" : "i-01b1d81668be33301"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "47z1cy9pv8vfy3kpftip7m0rm"
        } ]
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-e89a0a513c5a4bb9da727278797b5cfe",
      "type" : "HOSTMONITOR",
      "hostRef" : {
        "hostId" : "i-01b1d81668be33301"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "6h5qgv3exyc5vninphwhq2qi"
        } ]
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-e89a0a513c5a4bb9da727278797b5cfe",
      "type" : "REPORTSMANAGER",
      "hostRef" : {
        "hostId" : "i-01b1d81668be33301"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "eljcyk81exewvcskkaggvfik8"
        } ]
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-e89a0a513c5a4bb9da727278797b5cfe",
      "type" : "SERVICEMONITOR",
      "hostRef" : {
        "hostId" : "i-01b1d81668be33301"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "71cuv0fd75apbkn41qe1zu40v"
        } ]
      }
    } ],
    "displayName" : "Cloudera Management Service"
  },
  "managerSettings" : {
    "items" : [ {
      "name" : "AD_USE_SIMPLE_AUTH",
      "value" : "false"
    }, {
      "name" : "CLUSTER_STATS_START",
      "value" : "10/22/2012 22:40"
    }, {
      "name" : "KDC_ADMIN_PASSWORD",
      "value" : "BQIAAAA9AAEACkRBTklFTC5DT00ADGNsb3VkZXJhLXNjbQAAAAFZ1PSNAQAXABARoBxKDy8ih5bJP6DKGmNNAAAAAQ=="
    }, {
      "name" : "KDC_ADMIN_USER",
      "value" : "cloudera-scm@DANIEL.COM"
    }, {
      "name" : "KDC_HOST",
      "value" : "ip-172-31-11-253.us-east-2.compute.internal"
    }, {
      "name" : "KRB_ENC_TYPES",
      "value" : "arcfour-hmac"
    }, {
      "name" : "KRB_MANAGE_KRB5_CONF",
      "value" : "true"
    }, {
      "name" : "PUBLIC_CLOUD_STATUS",
      "value" : "ON_PUBLIC_CLOUD"
    }, {
      "name" : "REMOTE_PARCEL_REPO_URLS",
      "value" : "https://archive.cloudera.com/cdh5/parcels/{latest_supported}/,https://archive.cloudera.com/cdh4/parcels/latest/,https://archive.cloudera.com/impala/parcels/latest/,https://archive.cloudera.com/search/parcels/latest/,https://archive.cloudera.com/accumulo/parcels/1.4/,https://archive.cloudera.com/accumulo-c5/parcels/latest/,https://archive.cloudera.com/kafka/parcels/latest/,https://archive.cloudera.com/navigator-keytrustee5/parcels/latest/,https://archive.cloudera.com/spark/parcels/latest/,https://archive.cloudera.com/sqoop-connectors/parcels/latest/"
    }, {
      "name" : "SECURITY_REALM",
      "value" : "DANIEL.COM"
    } ]
  }
}
```

