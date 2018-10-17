* Start
```
[grcancelliere@grcsebcm ~]$ curl X POST -u grcancelliere:cloudera 'http://grcsebcm:7180/api/v1/clusters/grcancelliere/services/hive/commands/start'
{
  "id" : 570,
  "name" : "Start",
  "startTime" : "2018-10-17T09:25:25.710Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}
```
* Stop
```
[grcancelliere@grcsebcm ~]$ curl -X POST -u grcancelliere:cloudera 'http://grcsebcm:7180/api/v1/clusters/grcancelliere/services/hive/commands/stop'
{
  "id" : 565,
  "name" : "Stop",
  "startTime" : "2018-10-17T09:24:46.789Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}
```
* Status
```
[grcancelliere@grcsebcm ~]$ curl -X GET -u grcancelliere:cloudera 'http://grcsebcm:7180/api/v1/clusters/grcancelliere/services/hive'
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://grcsebcm:7180/cmf/serviceRedirect/hive",
  "serviceState" : "STARTED",
  "healthSummary" : "GOOD",
  "healthChecks" : [ {
    "name" : "HIVE_HIVEMETASTORES_HEALTHY",
    "summary" : "GOOD"
  }, {
    "name" : "HIVE_HIVESERVER2S_HEALTHY",
    "summary" : "GOOD"
  }, {
    "name" : "HIVE_WEBHCATS_HEALTHY",
    "summary" : "GOOD"
  } ],
  "configStale" : false
}
```