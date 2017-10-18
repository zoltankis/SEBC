# Check Hive Status
```
[centos@ip-172-32-11-139 ~]$ curl -u "zoltankis:cloudera" http://172.32.6.254:7180/api/v2/clusters/zoltankis/services/hive
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://ip-172-32-6-254.eu-central-1.compute.internal:7180/cmf/serviceRedirect/hive",
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

# Stop Hive
```
[centos@ip-172-32-11-139 ~]$curl -X POST -u zoltankis:cloudera  http://172.32.6.254:7180/api/v2/clusters/zoltankis/services/hive/commands/stop
{
  "id" : 386,
  "name" : "Stop",
  "startTime" : "2017-10-18T07:46:46.668Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}[
```
# Check Hive is Stopped
```
[centos@ip-172-32-11-139 ~]$ curl -u "zoltankis:cloudera" http://172.32.6.254:7180/api/v2/clusters/zoltankis/services/hive
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://ip-172-32-6-254.eu-central-1.compute.internal:7180/cmf/serviceRedirect/hive",
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

# Start Hive
```
[centos@ip-172-32-11-139 ~]$ curl -X POST -u zoltankis:cloudera  http://172.32.6.254:7180/api/v2/clusters/zoltankis/services/hive/commands/start
{
  "id" : 390,
  "name" : "Start",
  "startTime" : "2017-10-18T07:48:36.474Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}
```
# Check Hive is Started
```
[centos@ip-172-32-11-139 ~]$ curl -u "zoltankis:cloudera" http://172.32.6.254:7180/api/v2/clusters/zoltankis/services/hive
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://ip-172-32-6-254.eu-central-1.compute.internal:7180/cmf/serviceRedirect/hive",
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