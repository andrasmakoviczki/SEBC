# Result of cluster deployment

```
curl -u andrasmakoviczki:cloudera http://35.158.41.226:7180/api/v2/cm/deployment
```

```
{
  "timestamp" : "2017-10-18T07:46:03.763Z",
  "clusters" : [ {
    "name" : "Cluster 1",
    "version" : "CDH5",
    "services" : [ {
      "name" : "hive",
      "type" : "HIVE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "HIVEMETASTORE",
          "items" : [ {
            "name" : "hive_metastore_java_heapsize",
            "value" : "775946240"
          } ]
        }, {
          "roleType" : "HIVESERVER2",
          "items" : [ {
            "name" : "hiveserver2_java_heapsize",
            "value" : "775946240"
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
          "value" : "ip-172-32-4-188.eu-central-1.compute.internal"
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
        "name" : "hive-GATEWAY-bf5930e1d1f994331173ec2efcd416b8",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-015146f7feacfea97"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-HIVEMETASTORE-e15b314da34992c6501e61ba2859654c",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "i-059567d1d32321d7a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5qvjcd5uo2fw6rksysb7uz1ov"
          } ]
        }
      }, {
        "name" : "hive-HIVESERVER2-e15b314da34992c6501e61ba2859654c",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "i-059567d1d32321d7a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "dfh3hp65ov9xy6m1q9qyayt9m"
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
            "value" : "775946240"
          } ]
        } ],
        "items" : [ ]
      },
      "roles" : [ {
        "name" : "zookeeper-SERVER-835e6a41f03a82c341115c689226cc3f",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-05d0a89ac04b8245c"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "57rcqg8npzn09jnlmrpb4z0ap"
          }, {
            "name" : "serverId",
            "value" : "1"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-e15b314da34992c6501e61ba2859654c",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-059567d1d32321d7a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "b58szw2dcu7so87eq2fn45ou5"
          }, {
            "name" : "serverId",
            "value" : "3"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-ff08a393e6f0739738366e9e3b6099e3",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-09c638164377b2e81"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5uhhlqid9fi32237m6qhgkilj"
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
          "value" : "ip-172-32-4-188.eu-central-1.compute.internal"
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
          "value" : "hdfs-HTTPFS-e15b314da34992c6501e61ba2859654c"
        }, {
          "name" : "oozie_service",
          "value" : "oozie"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hue-HUE_SERVER-bf5930e1d1f994331173ec2efcd416b8",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "i-015146f7feacfea97"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5pgflnvgpco3cxguhtaxix5gr"
          }, {
            "name" : "secret_key",
            "value" : "ASXrbhZA8dVhTrb9I9k0A8s5rk7gYU"
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
            "value" : "ip-172-32-4-188.eu-central-1.compute.internal"
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
            "value" : "775946240"
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
        "name" : "oozie-OOZIE_SERVER-e15b314da34992c6501e61ba2859654c",
        "type" : "OOZIE_SERVER",
        "hostRef" : {
          "hostId" : "i-059567d1d32321d7a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3li75q81x1ffoykdpomulbsci"
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
            "value" : "6"
          }, {
            "name" : "mapred_submit_replication",
            "value" : "2"
          } ]
        }, {
          "roleType" : "JOBHISTORY",
          "items" : [ {
            "name" : "mr2_jobhistory_java_heapsize",
            "value" : "775946240"
          } ]
        }, {
          "roleType" : "NODEMANAGER",
          "items" : [ {
            "name" : "node_manager_java_heapsize",
            "value" : "775946240"
          }, {
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
            "value" : "775946240"
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
          "value" : "true"
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
          "value" : "J9XJXVQejhxslOBKm6OcHD0RhK5W6p"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "yarn-GATEWAY-bf5930e1d1f994331173ec2efcd416b8",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-015146f7feacfea97"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "yarn-JOBHISTORY-e15b314da34992c6501e61ba2859654c",
        "type" : "JOBHISTORY",
        "hostRef" : {
          "hostId" : "i-059567d1d32321d7a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6i99hsz4bc71jmifu4j9fg9bf"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-8351e0eecb799cdccd7713120bdcaa1c",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-08d08179bc8ab1ee1"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "20zd0ykd9u0dsar41damgnx7u"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-835e6a41f03a82c341115c689226cc3f",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-05d0a89ac04b8245c"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "bry50t36t2659bc5s52na82q7"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-e15b314da34992c6501e61ba2859654c",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-059567d1d32321d7a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "cea2kut73nliz2lmfrjbbvjsb"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-ff08a393e6f0739738366e9e3b6099e3",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-09c638164377b2e81"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "e2vbub8a1auva5egiw4qb3qnj"
          } ]
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-e15b314da34992c6501e61ba2859654c",
        "type" : "RESOURCEMANAGER",
        "hostRef" : {
          "hostId" : "i-059567d1d32321d7a"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_id",
            "value" : "92"
          }, {
            "name" : "role_jceks_password",
            "value" : "9c1c7hmggrz8xsbuuvrhzrrrd"
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
            "value" : "775946240"
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
            "value" : "775946240"
          } ]
        }, {
          "roleType" : "SECONDARYNAMENODE",
          "items" : [ {
            "name" : "fs_checkpoint_dir_list",
            "value" : "/dfs/snn"
          }, {
            "name" : "secondary_namenode_java_heapsize",
            "value" : "775946240"
          } ]
        } ],
        "items" : [ {
          "name" : "dfs_ha_fencing_cloudera_manager_secret_key",
          "value" : "b22tRVNt6ZVCTwoz9OmHJXfBdjFs9l"
        }, {
          "name" : "dfs_ha_fencing_methods",
          "value" : "shell(true)"
        }, {
          "name" : "fc_authorization_secret_key",
          "value" : "F7KQ7tpKLegUxYSmS0eATTgw6ZXUgX"
        }, {
          "name" : "http_auth_signature_secret",
          "value" : "NBOpAf2qhZBbztHuIztAYcMw2MX5j7"
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
        "name" : "hdfs-BALANCER-e15b314da34992c6501e61ba2859654c",
        "type" : "BALANCER",
        "hostRef" : {
          "hostId" : "i-059567d1d32321d7a"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-DATANODE-8351e0eecb799cdccd7713120bdcaa1c",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-08d08179bc8ab1ee1"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6cxpy7euoj8ppw6rvo8ww6qx6"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-835e6a41f03a82c341115c689226cc3f",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-05d0a89ac04b8245c"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7lr6gv9w9rpwb0q7g79rq6psi"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-e15b314da34992c6501e61ba2859654c",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-059567d1d32321d7a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "57ziw9in7m4mfwmbtk96x2zup"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-ff08a393e6f0739738366e9e3b6099e3",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-09c638164377b2e81"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "ees165hw3vrh91h52ys359cr"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-835e6a41f03a82c341115c689226cc3f",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "i-05d0a89ac04b8245c"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5e5h153dku8pl0wz10j4s6meq"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-e15b314da34992c6501e61ba2859654c",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "i-059567d1d32321d7a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "bbt6932y249m1bdi1190nc7hj"
          } ]
        }
      }, {
        "name" : "hdfs-GATEWAY-bf5930e1d1f994331173ec2efcd416b8",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-015146f7feacfea97"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-HTTPFS-e15b314da34992c6501e61ba2859654c",
        "type" : "HTTPFS",
        "hostRef" : {
          "hostId" : "i-059567d1d32321d7a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9ovsz1ky9xuygh7uhc4aucj82"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-835e6a41f03a82c341115c689226cc3f",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-05d0a89ac04b8245c"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4e6kcnan4c1sv8a3wvuz3e37x"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-e15b314da34992c6501e61ba2859654c",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-059567d1d32321d7a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3zzjslhwog7ljh0rydolcebbj"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-ff08a393e6f0739738366e9e3b6099e3",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-09c638164377b2e81"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "60cbb8hb7m7psme4b4lkrzu91"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-835e6a41f03a82c341115c689226cc3f",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "i-05d0a89ac04b8245c"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice"
          }, {
            "name" : "namenode_id",
            "value" : "103"
          }, {
            "name" : "role_jceks_password",
            "value" : "es6q129diekkzphd118t9e4qh"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-e15b314da34992c6501e61ba2859654c",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "i-059567d1d32321d7a"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice"
          }, {
            "name" : "namenode_id",
            "value" : "95"
          }, {
            "name" : "role_jceks_password",
            "value" : "cnfdy2s1au8v6mw5vtbvwuv8v"
          } ]
        }
      } ],
      "displayName" : "HDFS"
    } ]
  } ],
  "hosts" : [ {
    "hostId" : "i-09c638164377b2e81",
    "ipAddress" : "172.32.0.33",
    "hostname" : "ip-172-32-0-33.eu-central-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-05d0a89ac04b8245c",
    "ipAddress" : "172.32.1.46",
    "hostname" : "ip-172-32-1-46.eu-central-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-059567d1d32321d7a",
    "ipAddress" : "172.32.4.188",
    "hostname" : "ip-172-32-4-188.eu-central-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-08d08179bc8ab1ee1",
    "ipAddress" : "172.32.7.140",
    "hostname" : "ip-172-32-7-140.eu-central-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-015146f7feacfea97",
    "ipAddress" : "172.32.9.69",
    "hostname" : "ip-172-32-9-69.eu-central-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  } ],
  "users" : [ {
    "name" : "__cloudera_internal_user__mgmt-ACTIVITYMONITOR-ff08a393e6f0739738366e9e3b6099e3",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "80a1f7fc22e41f5938e0f9e434b14b7e2be84fbd5f0d4bde02766c09a9503c3c",
    "pwSalt" : 7985225265627345205,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-EVENTSERVER-ff08a393e6f0739738366e9e3b6099e3",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "16d24947d806a1c2b2529dd9fab0324309035be74d9b7bcc04ead7788db74009",
    "pwSalt" : -480112318732818207,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-HOSTMONITOR-ff08a393e6f0739738366e9e3b6099e3",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "b812d6dbe87a1c052b3645727f59d1e1ffefa8d95e6cbd1176bb76a1775d431d",
    "pwSalt" : 4144964594940084883,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-REPORTSMANAGER-ff08a393e6f0739738366e9e3b6099e3",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "b3c891ae51877370aebb581ce0ca8b366d4fa2ff4e5474a42c55e8923f742c27",
    "pwSalt" : 570731438325863847,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-SERVICEMONITOR-ff08a393e6f0739738366e9e3b6099e3",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "f470a6f5165bd95687316372c13da6163ef904521df595452b76c87035e54a0c",
    "pwSalt" : -2980702300132069692,
    "pwLogin" : true
  }, {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ],
    "pwHash" : "18810dc04c093ecc4371ecf4a2b4e9d4f757436ae4f5fd32c98d581b27579f59",
    "pwSalt" : 4759519176504697055,
    "pwLogin" : true
  }, {
    "name" : "andrasmakoviczki",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "390e2400edde6ef03ae6b8e0bc7886e21d38a72ef8c642c972860ea375b28402",
    "pwSalt" : -7008045775761049787,
    "pwLogin" : true
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ],
    "pwHash" : "7b3080c58a13f17560890b2cdabfa8af516f2a39525654afe6f0e19cbc40e524",
    "pwSalt" : -4405712690033222653,
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
          "value" : "ip-172-32-4-188.eu-central-1.compute.internal"
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
          "value" : "ip-172-32-4-188.eu-central-1.compute.internal"
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
      "name" : "mgmt-ACTIVITYMONITOR-ff08a393e6f0739738366e9e3b6099e3",
      "type" : "ACTIVITYMONITOR",
      "hostRef" : {
        "hostId" : "i-09c638164377b2e81"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "2fp83z88w8wjwigpm0xuzl4nk"
        } ]
      }
    }, {
      "name" : "mgmt-ALERTPUBLISHER-ff08a393e6f0739738366e9e3b6099e3",
      "type" : "ALERTPUBLISHER",
      "hostRef" : {
        "hostId" : "i-09c638164377b2e81"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "4i6r7f5hyi9ejaeydm7isu89y"
        } ]
      }
    }, {
      "name" : "mgmt-EVENTSERVER-ff08a393e6f0739738366e9e3b6099e3",
      "type" : "EVENTSERVER",
      "hostRef" : {
        "hostId" : "i-09c638164377b2e81"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "cq82mpzhsl4s34om6bvcq3til"
        } ]
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-ff08a393e6f0739738366e9e3b6099e3",
      "type" : "HOSTMONITOR",
      "hostRef" : {
        "hostId" : "i-09c638164377b2e81"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "arbgq3sr7gx0s257ynmvgd0ux"
        } ]
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-ff08a393e6f0739738366e9e3b6099e3",
      "type" : "REPORTSMANAGER",
      "hostRef" : {
        "hostId" : "i-09c638164377b2e81"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "8c6xdu8vhvj1tmp2dsvqp3cjx"
        } ]
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-ff08a393e6f0739738366e9e3b6099e3",
      "type" : "SERVICEMONITOR",
      "hostRef" : {
        "hostId" : "i-09c638164377b2e81"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "cpkjnz9paot91x7zfjox1cjih"
        } ]
      }
    } ],
    "displayName" : "Cloudera Management Service"
  },
  "managerSettings" : {
    "items" : [ {
      "name" : "CLUSTER_STATS_START",
      "value" : "10/22/2012 9:10"
    }, {
      "name" : "PUBLIC_CLOUD_STATUS",
      "value" : "ON_PUBLIC_CLOUD"
    }, {
      "name" : "REMOTE_PARCEL_REPO_URLS",
      "value" : "http://archive.cloudera.com/cdh5/parcels/5.8.3/,https://archive.cloudera.com/accumulo/parcels/1.4/,https://archive.cloudera.com/accumulo-c5/parcels/latest/,https://archive.cloudera.com/kafka/parcels/latest/,https://archive.cloudera.com/navigator-keytrustee5/parcels/latest/,https://archive.cloudera.com/spark/parcels/latest/,https://archive.cloudera.com/sqoop-connectors/parcels/latest/"
    } ]
  }
}
```