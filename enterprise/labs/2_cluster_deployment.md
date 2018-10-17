```
{
  "timestamp" : "2018-10-17T08:53:02.087Z",
  "clusters" : [ {
    "name" : "grcancelliere",
    "version" : "CDH5",
    "services" : [ {
      "name" : "zookeeper",
      "type" : "ZOOKEEPER",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ ]
      },
      "roles" : [ {
        "name" : "zookeeper-SERVER-191a8cef07a976e97b271a210bc7b5d2",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "2eb339df-49ca-487c-981a-4123cc136d06"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "aof58nj4rriytqshic2hl5d4c"
          }, {
            "name" : "serverId",
            "value" : "2"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-5695b8d2cb4baef892b8949d03fba0ba",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "fef03f72-f10b-492d-8c1c-801009d34af6"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "epbbxw8d7qv7070ngj7nasojs"
          }, {
            "name" : "serverId",
            "value" : "1"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-95da0bd10c88501636aff22a96ac576d",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "f0b6eefa-f58b-4893-b1fc-476e5637dedb"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "cvosudw4xcr9qtk1ojozczhi9"
          }, {
            "name" : "serverId",
            "value" : "3"
          } ]
        }
      } ],
      "displayName" : "ZooKeeper"
    }, {
      "name" : "oozie",
      "type" : "OOZIE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "OOZIE_SERVER",
          "items" : [ {
            "name" : "oozie_database_host",
            "value" : "grcsebcm"
          }, {
            "name" : "oozie_database_password",
            "value" : "<password>"
          }, {
            "name" : "oozie_database_type",
            "value" : "mysql"
          }, {
            "name" : "oozie_database_user",
            "value" : "oozie"
          }, {
            "name" : "oozie_java_heapsize",
            "value" : "803209216"
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
        "name" : "oozie-OOZIE_SERVER-36707c5a35561cdddfd74ee6f5ff17a0",
        "type" : "OOZIE_SERVER",
        "hostRef" : {
          "hostId" : "84b2241f-9a36-4dae-94b4-618fdff88b50"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1u663ex3qvq34a9gaf7f6t3z4"
          } ]
        }
      } ],
      "displayName" : "Oozie"
    }, {
      "name" : "hue",
      "type" : "HUE",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ {
          "name" : "database_host",
          "value" : "grcsebcm"
        }, {
          "name" : "database_password",
          "value" : "huepw"
        }, {
          "name" : "database_type",
          "value" : "mysql"
        }, {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "hue_webhdfs",
          "value" : "hdfs-HTTPFS-36707c5a35561cdddfd74ee6f5ff17a0"
        }, {
          "name" : "oozie_service",
          "value" : "oozie"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hue-HUE_SERVER-36707c5a35561cdddfd74ee6f5ff17a0",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "84b2241f-9a36-4dae-94b4-618fdff88b50"
        },
        "config" : {
          "items" : [ {
            "name" : "navmetadataserver_cmdb_password",
            "value" : "6fe6339a-c4f2-4f3f-a21c-d1097189ab72"
          }, {
            "name" : "role_jceks_password",
            "value" : "5eewk7lhzphsa6m235xx5gwag"
          }, {
            "name" : "secret_key",
            "value" : "3OyK9CzVti3GDvMRuY90Wl3FxfgdqP"
          } ]
        }
      } ],
      "displayName" : "Hue"
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
            "value" : "/data/1/dfs/dn,/data/2/dfs/dn"
          }, {
            "name" : "dfs_datanode_failed_volumes_tolerated",
            "value" : "1"
          }, {
            "name" : "dfs_datanode_max_locked_memory",
            "value" : "4294967296"
          }, {
            "name" : "rm_cpu_shares",
            "value" : "200"
          }, {
            "name" : "rm_io_weight",
            "value" : "100"
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
            "value" : "/data/dfs/jn"
          } ]
        }, {
          "roleType" : "NAMENODE",
          "items" : [ {
            "name" : "dfs_name_dir_list",
            "value" : "/data/1/dfs/nn,/data/2/dfs/nn"
          }, {
            "name" : "dfs_namenode_servicerpc_address",
            "value" : "8022"
          }, {
            "name" : "namenode_java_heapsize",
            "value" : "2373976064"
          } ]
        }, {
          "roleType" : "SECONDARYNAMENODE",
          "items" : [ {
            "name" : "fs_checkpoint_dir_list",
            "value" : "/data/dfs/snn"
          }, {
            "name" : "secondary_namenode_java_heapsize",
            "value" : "2373976064"
          } ]
        } ],
        "items" : [ {
          "name" : "dfs_client_use_datanode_hostname",
          "value" : "true"
        }, {
          "name" : "dfs_ha_fencing_cloudera_manager_secret_key",
          "value" : "7svUm3Hi80JhAUoMX0E4yZdlt4AHhN"
        }, {
          "name" : "fc_authorization_secret_key",
          "value" : "ofRFiXb2sCaGrApQvBK1a5pccDIb8r"
        }, {
          "name" : "http_auth_signature_secret",
          "value" : "OpEqdAtPUM2ZlAFX9yfZIwV9fTPIUA"
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
        "name" : "hdfs-BALANCER-191a8cef07a976e97b271a210bc7b5d2",
        "type" : "BALANCER",
        "hostRef" : {
          "hostId" : "2eb339df-49ca-487c-981a-4123cc136d06"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-DATANODE-5695b8d2cb4baef892b8949d03fba0ba",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "fef03f72-f10b-492d-8c1c-801009d34af6"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "80xsupxl2cs0k5phcee0o40xx"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-8246a7f03a5e767255e1dc283438077e",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "88b43579-3d32-413a-8f6e-452e46eeecb4"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "2nsnesfqym7dvbeao02dos2k"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-95da0bd10c88501636aff22a96ac576d",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "f0b6eefa-f58b-4893-b1fc-476e5637dedb"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "c6xs70sk6ecf65ix11csazw8z"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-191a8cef07a976e97b271a210bc7b5d2",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "2eb339df-49ca-487c-981a-4123cc136d06"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7vzizkeqwrv3q9qga9kyb7m69"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-95da0bd10c88501636aff22a96ac576d",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "f0b6eefa-f58b-4893-b1fc-476e5637dedb"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "dt1ypsehn2e6fykirrufv7zbh"
          } ]
        }
      }, {
        "name" : "hdfs-HTTPFS-36707c5a35561cdddfd74ee6f5ff17a0",
        "type" : "HTTPFS",
        "hostRef" : {
          "hostId" : "84b2241f-9a36-4dae-94b4-618fdff88b50"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "8zupfv0mjk8zuw74es2btrkqr"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-5695b8d2cb4baef892b8949d03fba0ba",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "fef03f72-f10b-492d-8c1c-801009d34af6"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4vzmotw95252vok1wklyh2nll"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-8246a7f03a5e767255e1dc283438077e",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "88b43579-3d32-413a-8f6e-452e46eeecb4"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7fdh4kv2qvsqtizwaf8nwh8ah"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-95da0bd10c88501636aff22a96ac576d",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "f0b6eefa-f58b-4893-b1fc-476e5637dedb"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7bhpcitqmmno94aiisqn5hrk3"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-191a8cef07a976e97b271a210bc7b5d2",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "2eb339df-49ca-487c-981a-4123cc136d06"
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
            "value" : "48"
          }, {
            "name" : "role_jceks_password",
            "value" : "enpw55a5td1g125qlxfw6yj7y"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-95da0bd10c88501636aff22a96ac576d",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "f0b6eefa-f58b-4893-b1fc-476e5637dedb"
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
            "value" : "68"
          }, {
            "name" : "role_jceks_password",
            "value" : "1hsxu0qcu8014r5befc64si96"
          } ]
        }
      } ],
      "displayName" : "HDFS"
    }, {
      "name" : "yarn",
      "type" : "YARN",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "mapred_reduce_tasks",
            "value" : "4"
          }, {
            "name" : "mapred_submit_replication",
            "value" : "3"
          } ]
        }, {
          "roleType" : "NODEMANAGER",
          "items" : [ {
            "name" : "container_executor_banned_users",
            "value" : "hdfs,yarn,bin"
          }, {
            "name" : "rm_cpu_shares",
            "value" : "1800"
          }, {
            "name" : "rm_io_weight",
            "value" : "900"
          }, {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100"
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/data/1/yarn/nm,/data/2/yarn/nm"
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/data/yarn/container-logs"
          }, {
            "name" : "yarn_nodemanager_resource_cpu_vcores",
            "value" : "3"
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "2457"
          } ]
        }, {
          "roleType" : "RESOURCEMANAGER",
          "items" : [ {
            "name" : "yarn_scheduler_maximum_allocation_mb",
            "value" : "3789"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_vcores",
            "value" : "3"
          } ]
        } ],
        "items" : [ {
          "name" : "cm_yarn_container_usage_job_user",
          "value" : "mapred"
        }, {
          "name" : "cm_yarn_enable_container_usage_aggregation",
          "value" : "true"
        }, {
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
          "value" : "HtKEwSA20qzzLPvLdeosU9PVCwNjjv"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "yarn-GATEWAY-36707c5a35561cdddfd74ee6f5ff17a0",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "84b2241f-9a36-4dae-94b4-618fdff88b50"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "yarn-JOBHISTORY-191a8cef07a976e97b271a210bc7b5d2",
        "type" : "JOBHISTORY",
        "hostRef" : {
          "hostId" : "2eb339df-49ca-487c-981a-4123cc136d06"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "bcard0a5uffu7e4t08jilbiwj"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-5695b8d2cb4baef892b8949d03fba0ba",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "fef03f72-f10b-492d-8c1c-801009d34af6"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "60un7v0t3f58bn2ilxxmxj85u"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-8246a7f03a5e767255e1dc283438077e",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "88b43579-3d32-413a-8f6e-452e46eeecb4"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "84m7y037dd8x5cvwabfoob6g5"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-95da0bd10c88501636aff22a96ac576d",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "f0b6eefa-f58b-4893-b1fc-476e5637dedb"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "bc1blyn85i0cq5f4h0cpduz52"
          } ]
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-191a8cef07a976e97b271a210bc7b5d2",
        "type" : "RESOURCEMANAGER",
        "hostRef" : {
          "hostId" : "2eb339df-49ca-487c-981a-4123cc136d06"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_id",
            "value" : "54"
          }, {
            "name" : "role_jceks_password",
            "value" : "383179767rgq1lmeygqpu3qm1"
          } ]
        }
      } ],
      "displayName" : "YARN (MR2 Included)"
    }, {
      "name" : "hive",
      "type" : "HIVE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "HIVEMETASTORE",
          "items" : [ {
            "name" : "hive_metastore_java_heapsize",
            "value" : "803209216"
          } ]
        }, {
          "roleType" : "HIVESERVER2",
          "items" : [ {
            "name" : "hiveserver2_java_heapsize",
            "value" : "803209216"
          }, {
            "name" : "hiveserver2_spark_driver_memory",
            "value" : "966367641"
          }, {
            "name" : "hiveserver2_spark_executor_cores",
            "value" : "4"
          }, {
            "name" : "hiveserver2_spark_executor_memory",
            "value" : "3216664166"
          }, {
            "name" : "hiveserver2_spark_yarn_driver_memory_overhead",
            "value" : "102"
          }, {
            "name" : "hiveserver2_spark_yarn_executor_memory_overhead",
            "value" : "541"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_metastore_database_host",
          "value" : "grcsebcm"
        }, {
          "name" : "hive_metastore_database_password",
          "value" : "hivepw"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hive-GATEWAY-191a8cef07a976e97b271a210bc7b5d2",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "2eb339df-49ca-487c-981a-4123cc136d06"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-36707c5a35561cdddfd74ee6f5ff17a0",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "84b2241f-9a36-4dae-94b4-618fdff88b50"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-5695b8d2cb4baef892b8949d03fba0ba",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "fef03f72-f10b-492d-8c1c-801009d34af6"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-8246a7f03a5e767255e1dc283438077e",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "88b43579-3d32-413a-8f6e-452e46eeecb4"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-95da0bd10c88501636aff22a96ac576d",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "f0b6eefa-f58b-4893-b1fc-476e5637dedb"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-HIVEMETASTORE-36707c5a35561cdddfd74ee6f5ff17a0",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "84b2241f-9a36-4dae-94b4-618fdff88b50"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "498r35uje2n5zuypudw19x0of"
          } ]
        }
      }, {
        "name" : "hive-HIVESERVER2-36707c5a35561cdddfd74ee6f5ff17a0",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "84b2241f-9a36-4dae-94b4-618fdff88b50"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "drwkjy7n5m0ywqlgsv2l3453b"
          } ]
        }
      }, {
        "name" : "hive-WEBHCAT-36707c5a35561cdddfd74ee6f5ff17a0",
        "type" : "WEBHCAT",
        "hostRef" : {
          "hostId" : "84b2241f-9a36-4dae-94b4-618fdff88b50"
        },
        "config" : {
          "items" : [ {
            "name" : "hive_webhcat_secret_key",
            "value" : "6oKQD0uqm0FZkmE4oF3ZzyEnndknSe"
          }, {
            "name" : "role_jceks_password",
            "value" : "5lhiiptr8mdnfbjlx0x1m0h2v"
          } ]
        }
      } ],
      "displayName" : "Hive"
    } ]
  } ],
  "hosts" : [ {
    "hostId" : "2eb339df-49ca-487c-981a-4123cc136d06",
    "ipAddress" : "10.1.0.7",
    "hostname" : "grcsebc1",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "f0b6eefa-f58b-4893-b1fc-476e5637dedb",
    "ipAddress" : "10.1.0.6",
    "hostname" : "grcsebc2",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "fef03f72-f10b-492d-8c1c-801009d34af6",
    "ipAddress" : "10.1.0.8",
    "hostname" : "grcsebc3",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "88b43579-3d32-413a-8f6e-452e46eeecb4",
    "ipAddress" : "10.1.0.9",
    "hostname" : "grcsebc4",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "84b2241f-9a36-4dae-94b4-618fdff88b50",
    "ipAddress" : "10.1.0.4",
    "hostname" : "grcsebcm",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  } ],
  "users" : [ {
    "name" : "__cloudera_internal_user__58221c4e-19d3-45e7-a7a8-c649231d6a9c",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "f36cc0973e3d708719b10931e55c2201e845adcb7251b76891022e072f06c157",
    "pwSalt" : 5822127760014230990,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__8a400956-671d-4fa4-8715-4cbabb2c2033",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "2ad3b2c48dcd1fb73d3ab0f647219f73d674229598fa5c40bf73a8c34eb26940",
    "pwSalt" : -4243115055773495304,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__hue-HUE_SERVER-36707c5a35561cdddfd74ee6f5ff17a0",
    "roles" : [ "ROLE_NAVIGATOR_ADMIN" ],
    "pwHash" : "c1d9c9c77c15b8ef0efffa0431f3c0d92d4bddfa28c9ae545427eba9db073e1e",
    "pwSalt" : 2282792392325149376,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-ACTIVITYMONITOR-36707c5a35561cdddfd74ee6f5ff17a0",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "8572dda0a38a0f28707ea5c9fb55db273f59c014cfb9650f48251cef8fca18c7",
    "pwSalt" : 7234667576669361790,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-EVENTSERVER-36707c5a35561cdddfd74ee6f5ff17a0",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "bd4d50493c59b7d0fc4e3b13c80f39402ae97eac976530f2655f568fc3ce1939",
    "pwSalt" : 1457284849116470257,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-HOSTMONITOR-36707c5a35561cdddfd74ee6f5ff17a0",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "1ce9670d707fb6c7f1b52590cdea8679b36be65403dcb78fa2f561d31cdb4257",
    "pwSalt" : 4454838065415748238,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-REPORTSMANAGER-36707c5a35561cdddfd74ee6f5ff17a0",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "3159b4d4f69dedfa2de31216789a82ca2249d3efff6ec09a39cb04f6b4a1e114",
    "pwSalt" : 4903370484908276160,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-SERVICEMONITOR-36707c5a35561cdddfd74ee6f5ff17a0",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "c090efa9b34354ce1488531a183b518ef19e45013a6113b923e20bc7d5b611b7",
    "pwSalt" : 3072667858822885663,
    "pwLogin" : true
  }, {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ],
    "pwHash" : "9e0cd2492c2f1f0b1affe5180399da6bc5fb40282103bcdea44ecfc98b0683c3",
    "pwSalt" : -3050513147480612679,
    "pwLogin" : true
  }, {
    "name" : "grcancelliere",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "caab807150c879c4509e63afb7afa28f45f0e8bdc6ca799cfcf333b418b26e9e",
    "pwSalt" : 8268824666182469699,
    "pwLogin" : true
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ],
    "pwHash" : "e7aa37e0243bb1b07aa84c1083e15df0f017e4ff02491d7cb3a1f0055d791d2f",
    "pwSalt" : -4686351796348664681,
    "pwLogin" : true
  } ],
  "versionInfo" : {
    "version" : "5.13.3",
    "buildUser" : "jenkins",
    "buildTimestamp" : "20180328-1830",
    "gitHash" : "f90c58536c252d70a23bde6d94514d92a1f111d4",
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
          "value" : "grcsebcm"
        }, {
          "name" : "firehose_database_name",
          "value" : "amon"
        }, {
          "name" : "firehose_database_password",
          "value" : "amonpw"
        }, {
          "name" : "firehose_database_user",
          "value" : "amon"
        }, {
          "name" : "firehose_heapsize",
          "value" : "803209216"
        } ]
      }, {
        "roleType" : "EVENTSERVER",
        "items" : [ {
          "name" : "event_server_heapsize",
          "value" : "803209216"
        } ]
      }, {
        "roleType" : "HOSTMONITOR",
        "items" : [ {
          "name" : "firehose_heapsize",
          "value" : "803209216"
        }, {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "1043333120"
        } ]
      }, {
        "roleType" : "REPORTSMANAGER",
        "items" : [ {
          "name" : "headlamp_database_host",
          "value" : "grcsebcm"
        }, {
          "name" : "headlamp_database_name",
          "value" : "rman"
        }, {
          "name" : "headlamp_database_password",
          "value" : "rmanpw"
        }, {
          "name" : "headlamp_database_user",
          "value" : "rman"
        }, {
          "name" : "headlamp_heapsize",
          "value" : "803209216"
        } ]
      }, {
        "roleType" : "SERVICEMONITOR",
        "items" : [ {
          "name" : "firehose_heapsize",
          "value" : "803209216"
        }, {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "1043333120"
        } ]
      } ],
      "items" : [ ]
    },
    "roles" : [ {
      "name" : "mgmt-ACTIVITYMONITOR-36707c5a35561cdddfd74ee6f5ff17a0",
      "type" : "ACTIVITYMONITOR",
      "hostRef" : {
        "hostId" : "84b2241f-9a36-4dae-94b4-618fdff88b50"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "drqqgkv76h978tu70c1kktts9"
        } ]
      }
    }, {
      "name" : "mgmt-ALERTPUBLISHER-36707c5a35561cdddfd74ee6f5ff17a0",
      "type" : "ALERTPUBLISHER",
      "hostRef" : {
        "hostId" : "84b2241f-9a36-4dae-94b4-618fdff88b50"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "arhdf08in5tn1ncugop8uioio"
        } ]
      }
    }, {
      "name" : "mgmt-EVENTSERVER-36707c5a35561cdddfd74ee6f5ff17a0",
      "type" : "EVENTSERVER",
      "hostRef" : {
        "hostId" : "84b2241f-9a36-4dae-94b4-618fdff88b50"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "2qaz0dn2tfrj455ymj3i3lzf7"
        } ]
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-36707c5a35561cdddfd74ee6f5ff17a0",
      "type" : "HOSTMONITOR",
      "hostRef" : {
        "hostId" : "84b2241f-9a36-4dae-94b4-618fdff88b50"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "5tm6xb3909buw1p4ptsax7hpa"
        } ]
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-36707c5a35561cdddfd74ee6f5ff17a0",
      "type" : "REPORTSMANAGER",
      "hostRef" : {
        "hostId" : "84b2241f-9a36-4dae-94b4-618fdff88b50"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "8bkwx36qs45kuls1dg82pp4za"
        } ]
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-36707c5a35561cdddfd74ee6f5ff17a0",
      "type" : "SERVICEMONITOR",
      "hostRef" : {
        "hostId" : "84b2241f-9a36-4dae-94b4-618fdff88b50"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "8k0s29yf42plrgh78qohniizx"
        } ]
      }
    } ],
    "displayName" : "Cloudera Management Service"
  },
  "managerSettings" : {
    "items" : [ {
      "name" : "CLUSTER_STATS_START",
      "value" : "10/26/2012 1:10"
    }, {
      "name" : "PUBLIC_CLOUD_STATUS",
      "value" : "NOT_ON_PUBLIC_CLOUD"
    }, {
      "name" : "REMOTE_PARCEL_REPO_URLS",
      "value" : "http://grcsebc2/cdh5/parcels/5.13.3/"
    } ]
  }
}
```