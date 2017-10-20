# Command and output for hdfs dfs -ls /user
```
[root@ip-172-32-9-114 ~]# hdfs dfs -ls /user
Found 6 items
drwxr-x---   - ernest  ernest           0 2017-10-20 08:53 /user/ernest
drwxrwxrwx   - mapred  hadoop           0 2017-10-20 08:49 /user/history
drwxrwxr-t   - hive    hive             0 2017-10-20 08:50 /user/hive
drwxrwxr-x   - hue     hue              0 2017-10-20 08:51 /user/hue
drwxrwxr-x   - oozie   oozie            0 2017-10-20 08:51 /user/oozie
drwxr-x---   - siwicki siwicki          0 2017-10-20 08:53 /user/siwicki
```

# The output from the CM API call ../api/v14/hosts
```
[root@ip-172-32-9-114 ~]# curl -X GET -u "admin:admin" http://$(hostname -i):7180/api/v14/hosts
{
  "items" : [ {
    "hostId" : "i-007c67701174fcac7",
    "ipAddress" : "172.32.1.58",
    "hostname" : "ip-172-32-1-58.eu-central-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-32-9-114.eu-central-1.compute.internal:7180/cmf/hostRedirect/i-007c67701174fcac7",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15664549888
  }, {
    "hostId" : "i-02edea8bcd661a22f",
    "ipAddress" : "172.32.13.100",
    "hostname" : "ip-172-32-13-100.eu-central-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-32-9-114.eu-central-1.compute.internal:7180/cmf/hostRedirect/i-02edea8bcd661a22f",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15664549888
  }, {
    "hostId" : "i-029b5158d1c0043e8",
    "ipAddress" : "172.32.4.7",
    "hostname" : "ip-172-32-4-7.eu-central-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-32-9-114.eu-central-1.compute.internal:7180/cmf/hostRedirect/i-029b5158d1c0043e8",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15664549888
  }, {
    "hostId" : "i-0166c4cf2a1e6d418",
    "ipAddress" : "172.32.9.114",
    "hostname" : "ip-172-32-9-114.eu-central-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-32-9-114.eu-central-1.compute.internal:7180/cmf/hostRedirect/i-0166c4cf2a1e6d418",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15664549888
  }, {
    "hostId" : "i-05454342671643da2",
    "ipAddress" : "172.32.9.200",
    "hostname" : "ip-172-32-9-200.eu-central-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-32-9-114.eu-central-1.compute.internal:7180/cmf/hostRedirect/i-05454342671643da2",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15664549888
  } ]
}[
```