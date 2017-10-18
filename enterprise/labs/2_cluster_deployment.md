# Store the output in enterprise/labs/2_cluster_deployment.md
```
[centos@ip-172-32-11-139 ~]$ curl -X GET -u "zoltankis:cloudera" -i http://172.32.6.254:7180/api/v2/cm/deployment
HTTP/1.1 200 OK
Expires: Thu, 01-Jan-1970 00:00:00 GMT
Set-Cookie: CLOUDERA_MANAGER_SESSIONID=19yx23ispsrc71myaoolo3xe96;Path=/;HttpOnly
Content-Type: application/json
Date: Wed, 18 Oct 2017 07:38:03 GMT
Transfer-Encoding: chunked
Server: Jetty(6.1.26.cloudera.4)

{
  "timestamp" : "2017-10-18T07:38:03.605Z",
  "clusters" : [ {
    "name" : "zoltankis",
    "version" : "CDH5",
    "services" : [ {
      "name" : "hive",
      "type" : "HIVE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "HIVEMETASTORE",
          "items" : [ {
            "name" : "hive_metastore_java_heapsize",
            "value" : "439353344"
          } ]
        }, {
          "roleType" : "HIVESERVER2",
          "items" : [ {
            "name" : "hiveserver2_java_heapsize",
            "value" : "439353344"
          }, {
            "name" : "hiveserver2_spark_driver_memory",
            "value" : "966367641"
          }, {
            "name" : "hiveserver2_spark_executor_cores",
            "value" : "4"
          }, {
            "name" : "hiveserver2_spark_executor_memory",
            "value" : "912680550"
          }, {
            "name" : "hiveserver2_spark_yarn_driver_memory_overhead",
            "value" : "102"
          }, {
            "name" : "hiveserver2_spark_yarn_executor_memory_overhead",
            "value" : "153"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_metastore_database_host",
          "value" : "ip-172-32-6-254.eu-central-1.compute.internal"
        }, {
          "name" : "hive_metastore_database_password",
          "value" : "password"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hive-GATEWAY-740148bb2a48b9c818124d89c263d7e1",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-0e1f45a44552f5e53"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-HIVEMETASTORE-4a395f01b295b51da255de59bd4ae435",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "i-0ffadff0974fbdac6"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "bwb4pv5ke9e8m9hyoysv36jnv"
          } ]
        }
      }, {
        "name" : "hive-HIVESERVER2-4a395f01b295b51da255de59bd4ae435",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "i-0ffadff0974fbdac6"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "8qbd4ixp77718w94xjto9spyi"
          } ]
        }
      } ],
      "displayName" : "Hive"
    }, {
      "name" : "zookeeper",
      "type" : "ZOOKEEPER",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "SERVER",
          "items" : [ {
            "name" : "zookeeper_server_java_heapsize",
            "value" : "439353344"
          } ]
        } ],
        "items" : [ ]
      },
      "roles" : [ {
        "name" : "zookeeper-SERVER-1a439429830bd6a3c2db3b203e6cb828",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-0e01d9cee25392bc3"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7shnkros938c1zjh5vf2njeqp"
          }, {
            "name" : "serverId",
            "value" : "1"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-2e86b7cd879f524e751601dcc75abb5d",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-0d37f141d5aabdda8"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5h0s9m0zvszm2zkj1egeq8z1a"
          }, {
            "name" : "serverId",
            "value" : "3"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-4a395f01b295b51da255de59bd4ae435",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-0ffadff0974fbdac6"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "18u9cofbhegyqqdy2tdv0mh96"
          }, {
            "name" : "serverId",
            "value" : "2"
          } ]
        }
      } ],
      "displayName" : "ZooKeeper"
    }, {
      "name" : "hue",
      "type" : "HUE",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ {
          "name" : "database_host",
          "value" : "ip-172-32-6-254.eu-central-1.compute.internal"
        }, {
          "name" : "database_password",
          "value" : "password"
        }, {
          "name" : "database_type",
          "value" : "mysql"
        }, {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "hue_webhdfs",
          "value" : "hdfs-HTTPFS-4a395f01b295b51da255de59bd4ae435"
        }, {
          "name" : "oozie_service",
          "value" : "oozie"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hue-HUE_SERVER-740148bb2a48b9c818124d89c263d7e1",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "i-0e1f45a44552f5e53"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3qcceq4o3wbwgh3xrmtrz2brv"
          }, {
            "name" : "secret_key",
            "value" : "F1soKzlJBmqvybKiYYSvMkcEAyVV6J"
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
            "value" : "ip-172-32-6-254.eu-central-1.compute.internal"
          }, {
            "name" : "oozie_database_password",
            "value" : "password"
          }, {
            "name" : "oozie_database_type",
            "value" : "mysql"
          }, {
            "name" : "oozie_database_user",
            "value" : "oozie"
          }, {
            "name" : "oozie_java_heapsize",
            "value" : "439353344"
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
        "name" : "oozie-OOZIE_SERVER-4a395f01b295b51da255de59bd4ae435",
        "type" : "OOZIE_SERVER",
        "hostRef" : {
          "hostId" : "i-0ffadff0974fbdac6"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3vmxri6fxu5fycbc995lt5d9m"
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
            "value" : "8"
          }, {
            "name" : "mapred_submit_replication",
            "value" : "2"
          } ]
        }, {
          "roleType" : "JOBHISTORY",
          "items" : [ {
            "name" : "mr2_jobhistory_java_heapsize",
            "value" : "439353344"
          } ]
        }, {
          "roleType" : "NODEMANAGER",
          "items" : [ {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100"
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/yarn/nm"
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/yarn/container-logs"
          }, {
            "name" : "yarn_nodemanager_resource_cpu_vcores",
            "value" : "4"
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "3982"
          } ]
        }, {
          "roleType" : "RESOURCEMANAGER",
          "items" : [ {
            "name" : "resource_manager_java_heapsize",
            "value" : "439353344"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_mb",
            "value" : "5192"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_vcores",
            "value" : "3"
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
          "value" : "90"
        }, {
          "name" : "yarn_service_cgroups",
          "value" : "false"
        }, {
          "name" : "yarn_service_lce_always",
          "value" : "false"
        }, {
          "name" : "zk_authorization_secret_key",
          "value" : "oDKph0kLHCyM9mB3vBuIeHCHDelL5u"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "yarn-GATEWAY-740148bb2a48b9c818124d89c263d7e1",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-0e1f45a44552f5e53"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "yarn-JOBHISTORY-4a395f01b295b51da255de59bd4ae435",
        "type" : "JOBHISTORY",
        "hostRef" : {
          "hostId" : "i-0ffadff0974fbdac6"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "c733qpz2n9zmfk669xv6e1doz"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-1a439429830bd6a3c2db3b203e6cb828",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-0e01d9cee25392bc3"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "a37pvgzfist35bidms93qtnyh"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-2e86b7cd879f524e751601dcc75abb5d",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-0d37f141d5aabdda8"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1xuours16su2avlr4xolfafdb"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-4a395f01b295b51da255de59bd4ae435",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-0ffadff0974fbdac6"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "92xakekvgoxuulqa3syo2rs"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-654cc948ba906675a5fdf61723aff7b8",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-0a6ca768f83a6ef8e"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "22dqqfn7j3drgptitwumlyhow"
          } ]
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-4a395f01b295b51da255de59bd4ae435",
        "type" : "RESOURCEMANAGER",
        "hostRef" : {
          "hostId" : "i-0ffadff0974fbdac6"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_id",
            "value" : "48"
          }, {
            "name" : "role_jceks_password",
            "value" : "bkpsdzkjc8dqobxs8ymbl5cga"
          } ]
        }
      } ],
      "displayName" : "YARN (MR2 Included)"
    }, {
      "name" : "hdfs",
      "type" : "HDFS",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "BALANCER",
          "items" : [ {
            "name" : "balancer_java_heapsize",
            "value" : "439353344"
          } ]
        }, {
          "roleType" : "DATANODE",
          "items" : [ {
            "name" : "datanode_java_heapsize",
            "value" : "1073741824"
          }, {
            "name" : "dfs_data_dir_list",
            "value" : "/dfs/dn"
          }, {
            "name" : "dfs_datanode_du_reserved",
            "value" : "5270942105"
          }, {
            "name" : "dfs_datanode_max_locked_memory",
            "value" : "4294967296"
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
            "value" : "/dfs/jn"
          } ]
        }, {
          "roleType" : "NAMENODE",
          "items" : [ {
            "name" : "dfs_name_dir_list",
            "value" : "/dfs/nn"
          }, {
            "name" : "dfs_namenode_servicerpc_address",
            "value" : "8022"
          }, {
            "name" : "namenode_java_heapsize",
            "value" : "439353344"
          } ]
        }, {
          "roleType" : "SECONDARYNAMENODE",
          "items" : [ {
            "name" : "fs_checkpoint_dir_list",
            "value" : "/dfs/snn"
          }, {
            "name" : "secondary_namenode_java_heapsize",
            "value" : "439353344"
          } ]
        } ],
        "items" : [ {
          "name" : "dfs_ha_fencing_cloudera_manager_secret_key",
          "value" : "0VSOIr0gAvgvVv5cDvy6DBhxWpsOQr"
        }, {
          "name" : "dfs_ha_fencing_methods",
          "value" : "shell(true)"
        }, {
          "name" : "fc_authorization_secret_key",
          "value" : "pvpVTV7BAZudIXaXmyOkkhJ1sn6oRd"
        }, {
          "name" : "http_auth_signature_secret",
          "value" : "YA84NzffvO6E78CRJvgr5eAqwoXu93"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "10"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hdfs-BALANCER-4a395f01b295b51da255de59bd4ae435",
        "type" : "BALANCER",
        "hostRef" : {
          "hostId" : "i-0ffadff0974fbdac6"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-DATANODE-1a439429830bd6a3c2db3b203e6cb828",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-0e01d9cee25392bc3"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "czs1b2onggjegyu8alw0x17km"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-2e86b7cd879f524e751601dcc75abb5d",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-0d37f141d5aabdda8"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "a9xevjkl76bhsypkwqmg72csg"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-4a395f01b295b51da255de59bd4ae435",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-0ffadff0974fbdac6"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "tqgifmes4mdvkaztxbsxys3a"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-654cc948ba906675a5fdf61723aff7b8",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-0a6ca768f83a6ef8e"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3jk2518w2lbm9xzwhzctft5e5"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-1a439429830bd6a3c2db3b203e6cb828",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "i-0e01d9cee25392bc3"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6k54ukftgzsm1u4gmcs21p5f8"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-4a395f01b295b51da255de59bd4ae435",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "i-0ffadff0974fbdac6"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "55bfwipgolm2k2rxkiaw4hown"
          } ]
        }
      }, {
        "name" : "hdfs-GATEWAY-740148bb2a48b9c818124d89c263d7e1",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-0e1f45a44552f5e53"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-HTTPFS-4a395f01b295b51da255de59bd4ae435",
        "type" : "HTTPFS",
        "hostRef" : {
          "hostId" : "i-0ffadff0974fbdac6"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "2ov2aoy1dwqochx685ht59oe3"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-1a439429830bd6a3c2db3b203e6cb828",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-0e01d9cee25392bc3"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "783uaf4ekxx6pcugi4klytktm"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-2e86b7cd879f524e751601dcc75abb5d",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-0d37f141d5aabdda8"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4ssyyirot9v55nrsksl5jr9ip"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-4a395f01b295b51da255de59bd4ae435",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-0ffadff0974fbdac6"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3csiyztaftrvjm9ogeazknm2s"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-1a439429830bd6a3c2db3b203e6cb828",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "i-0e01d9cee25392bc3"
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
            "value" : "58"
          }, {
            "name" : "role_jceks_password",
            "value" : "30l09xqzf9fyn4brb7jkdlwm"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-4a395f01b295b51da255de59bd4ae435",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "i-0ffadff0974fbdac6"
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
            "value" : "51"
          }, {
            "name" : "role_jceks_password",
            "value" : "68rhn0b5r5kput2bw89u4bkp0"
          } ]
        }
      } ],
      "displayName" : "HDFS"
    } ]
  } ],
  "hosts" : [ {
    "hostId" : "i-0e1f45a44552f5e53",
    "ipAddress" : "172.32.11.139",
    "hostname" : "ip-172-32-11-139.eu-central-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-0e01d9cee25392bc3",
    "ipAddress" : "172.32.13.168",
    "hostname" : "ip-172-32-13-168.eu-central-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-0d37f141d5aabdda8",
    "ipAddress" : "172.32.6.238",
    "hostname" : "ip-172-32-6-238.eu-central-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-0ffadff0974fbdac6",
    "ipAddress" : "172.32.6.254",
    "hostname" : "ip-172-32-6-254.eu-central-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-0a6ca768f83a6ef8e",
    "ipAddress" : "172.32.6.75",
    "hostname" : "ip-172-32-6-75.eu-central-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  } ],
  "users" : [ {
    "name" : "__cloudera_internal_user__mgmt-ACTIVITYMONITOR-4a395f01b295b51da255de59bd4ae435",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "e394e8030ed8c459e8ff3fda807984d7533e5275fb4b078f6a335804ce42241c",
    "pwSalt" : -1604104393531028765,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-EVENTSERVER-4a395f01b295b51da255de59bd4ae435",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "05ee01c58580efedd0d0c581aef07613c8582b1a14f651bd16e206a008767e6c",
    "pwSalt" : 2845657161243143845,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-HOSTMONITOR-4a395f01b295b51da255de59bd4ae435",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "8ca7beb86321865651e201df87c8dd78229f477245125d49bf66bdabba1106d2",
    "pwSalt" : 2047007869394663042,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-REPORTSMANAGER-4a395f01b295b51da255de59bd4ae435",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "cbe522c4f5e629974312a1eea3ec2756cbe31d863aeaa68b7f8a4fbfea36dd43",
    "pwSalt" : 1240616185258909860,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-SERVICEMONITOR-4a395f01b295b51da255de59bd4ae435",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "5abe056f29b3df2ccdb8f031a69d69cbeb31a184cc6b97625c6c7c81af1dc6d9",
    "pwSalt" : 5662182264144393654,
    "pwLogin" : true
  }, {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ],
    "pwHash" : "fb1c06ffa44c6462a8978358132b980b1164fb4ee021424ac93e2489332a38ba",
    "pwSalt" : -8628287119722537096,
    "pwLogin" : true
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ],
    "pwHash" : "9c000833f7481eb6207dd250e28865b4ed38aca20bfcf5126ebce62e9a3cee14",
    "pwSalt" : 1999860831987713066,
    "pwLogin" : true
  }, {
    "name" : "zoltankis",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "323ff02940446525c35b28d6ff4d7e66356497b41a5700acdcc0027e3dcaf1f7",
    "pwSalt" : -7851399339025278965,
    "pwLogin" : true
  } ],
  "versionInfo" : {
    "version" : "5.8.3",
    "buildUser" : "jenkins",
    "buildTimestamp" : "20161019-1014",
    "gitHash" : "518f0d6d44abc87bc392646e4369a20c8192b7cf",
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
          "value" : "ip-172-32-6-254.eu-central-1.compute.internal"
        }, {
          "name" : "firehose_database_name",
          "value" : "amon"
        }, {
          "name" : "firehose_database_password",
          "value" : "password"
        }, {
          "name" : "firehose_database_user",
          "value" : "amon"
        }, {
          "name" : "firehose_heapsize",
          "value" : "439353344"
        } ]
      }, {
        "roleType" : "EVENTSERVER",
        "items" : [ {
          "name" : "event_server_heapsize",
          "value" : "439353344"
        } ]
      }, {
        "roleType" : "HOSTMONITOR",
        "items" : [ {
          "name" : "firehose_heapsize",
          "value" : "439353344"
        }, {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "805306368"
        } ]
      }, {
        "roleType" : "REPORTSMANAGER",
        "items" : [ {
          "name" : "headlamp_database_host",
          "value" : "ip-172-32-6-254.eu-central-1.compute.internal"
        }, {
          "name" : "headlamp_database_name",
          "value" : "rman"
        }, {
          "name" : "headlamp_database_password",
          "value" : "password"
        }, {
          "name" : "headlamp_database_user",
          "value" : "rman"
        }, {
          "name" : "headlamp_heapsize",
          "value" : "439353344"
        } ]
      }, {
        "roleType" : "SERVICEMONITOR",
        "items" : [ {
          "name" : "firehose_heapsize",
          "value" : "439353344"
        }, {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "805306368"
        } ]
      } ],
      "items" : [ ]
    },
    "roles" : [ {
      "name" : "mgmt-ACTIVITYMONITOR-4a395f01b295b51da255de59bd4ae435",
      "type" : "ACTIVITYMONITOR",
      "hostRef" : {
        "hostId" : "i-0ffadff0974fbdac6"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "c5kxuwlrnse9olsnp6s87s583"
        } ]
      }
    }, {
      "name" : "mgmt-ALERTPUBLISHER-4a395f01b295b51da255de59bd4ae435",
      "type" : "ALERTPUBLISHER",
      "hostRef" : {
        "hostId" : "i-0ffadff0974fbdac6"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "91bk1yelybsbc35dyfs9jaidt"
        } ]
      }
    }, {
      "name" : "mgmt-EVENTSERVER-4a395f01b295b51da255de59bd4ae435",
      "type" : "EVENTSERVER",
      "hostRef" : {
        "hostId" : "i-0ffadff0974fbdac6"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "45u2qmdcl1bcem36m5jo46jwn"
        } ]
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-4a395f01b295b51da255de59bd4ae435",
      "type" : "HOSTMONITOR",
      "hostRef" : {
        "hostId" : "i-0ffadff0974fbdac6"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "2m1sai2ukxuhzmh7kqmvk3s74"
        } ]
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-4a395f01b295b51da255de59bd4ae435",
      "type" : "REPORTSMANAGER",
      "hostRef" : {
        "hostId" : "i-0ffadff0974fbdac6"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "9c8lnx606orr6v3expq7iiaau"
        } ]
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-4a395f01b295b51da255de59bd4ae435",
      "type" : "SERVICEMONITOR",
      "hostRef" : {
        "hostId" : "i-0ffadff0974fbdac6"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "cvta46qzkmn16unagwreisy8p"
        } ]
      }
    } ],
    "displayName" : "Cloudera Management Service"
  },
  "managerSettings" : {
    "items" : [ {
      "name" : "CLUSTER_STATS_START",
      "value" : "10/23/2012 19:40"
    }, {
      "name" : "PUBLIC_CLOUD_STATUS",
      "value" : "ON_PUBLIC_CLOUD"
    }, {
      "name" : "REMOTE_PARCEL_REPO_URLS",
      "value" : "http://archive.cloudera.com/cdh5/parcels/5.8.3/,http://18.194.48.135/cdh5.8/"
    } ]
  }
}[
```