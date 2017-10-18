# Report the latest available version of the API
```
[root@ip-172-32-11-139 ~]# curl -X GET -u "zoltankis:cloudera" http://172.32.6.254:7180/api/version
v14
```
# Report the CM version
```
[root@ip-172-32-11-139 ~]# curl -X GET -u "zoltankis:cloudera" http://172.32.6.254:7180/api/v14/cm/version
{
  "version" : "5.9.3",
  "buildUser" : "jenkins",
  "buildTimestamp" : "20170627-1506",
  "gitHash" : "23506bb4e114dd460bdac64c57a672e6be631907",
  "snapshot" : false
}
```
# List all CM users
```
root@ip-172-32-11-139 ~]# curl -X GET -u "zoltankis:cloudera" http://172.32.6.254:7180/api/v14/users
{
  "items" : [ {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ]
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ]
  }, {
    "name" : "zoltankis",
    "roles" : [ "ROLE_ADMIN" ]
  } ]
}
```
# Report the database server in use by CM
```
[root@ip-172-32-11-139 ~]# curl -X GET -u "zoltankis:cloudera" http://172.32.6.254:7180/api/v14/cm/scmDbInfo
{
  "scmDbType" : "MYSQL",
  "embeddedDbUsed" : false
}
```