# API calls

## Hive service status
```
[root@ip-172-32-9-69 ~]# curl -u andrasmakoviczki:cloudera http://35.158.41.226:7180/api/v2/clusters/cluster/services/hive/
```

```
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://ip-172-32-4-188.eu-central-1.compute.internal:7180/cmf/serviceRedirect/hive",
  "serviceState" : "STARTED",
  "healthSummary" : "GOOD",
  "healthChecks" : [ {
    "name" : "HIVE_HIVEMETASTORES_HEALTHY",
    "summary" : "GOOD"
  }, {
    "name" : "HIVE_HIVESERVER2S_HEALTHY",
    "summary" : "GOOD"
  } ],
  "configStale" : false,
  "maintenanceMode" : false,
  "maintenanceOwners" : [ ],
  "displayName" : "Hive"
```

## Hive service stop

```
[root@ip-172-32-9-69 ~]# curl -X POST -u andrasmakoviczki:cloudera http://35.158.41.226:7180/api/v2/clusters/andrasmakoviczki/services/hive/commands/stop
```

```
{
  "id" : 754,
  "name" : "Stop",
  "startTime" : "2017-10-18T07:55:46.238Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}
```

```
[root@ip-172-32-9-69 ~]#curl -u andrasmakoviczki:cloudera http://35.158.41.226:7180/api/v2/clusters/cluster/services/hive/
```

```
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://ip-172-32-4-188.eu-central-1.compute.internal:7180/cmf/serviceRedirect/hive",
  "serviceState" : "STOPPED",
  "healthSummary" : "DISABLED",
  "healthChecks" : [ {
    "name" : "HIVE_HIVEMETASTORES_HEALTHY",
    "summary" : "DISABLED"
  }, {
    "name" : "HIVE_HIVESERVER2S_HEALTHY",
    "summary" : "DISABLED"
  } ],
  "configStale" : false,
  "maintenanceMode" : false,
  "maintenanceOwners" : [ ],
  "displayName" : "Hive"
}
```

## Hive service start

```
[root@ip-172-32-9-69 ~]# curl -X POST -u andrasmakoviczki:cloudera http://35.158.41.226:7180/api/v2/clusters/andrasmakoviczki/services/hive/commands/start
```

```
{
  "id" : 762,
  "name" : "Start",
  "startTime" : "2017-10-18T07:56:21.598Z",
  "endTime" : "2017-10-18T07:56:21.598Z",
  "active" : false,
  "success" : false,
  "resultMessage" : "Command Start is not currently available for execution.",
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}
```

```
[root@ip-172-32-9-69 ~]# curl -u andrasmakoviczki:cloudera http://35.158.41.226:7180/api/v2/clusters/cluster/services/hive/
```

```
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://ip-172-32-4-188.eu-central-1.compute.internal:7180/cmf/serviceRedirect/hive",
  "serviceState" : "STARTED",
  "healthSummary" : "GOOD",
  "healthChecks" : [ {
    "name" : "HIVE_HIVEMETASTORES_HEALTHY",
    "summary" : "GOOD"
  }, {
    "name" : "HIVE_HIVESERVER2S_HEALTHY",
    "summary" : "GOOD"
  } ],
  "configStale" : false,
  "maintenanceMode" : false,
  "maintenanceOwners" : [ ],
  "displayName" : "Hive"
}
```