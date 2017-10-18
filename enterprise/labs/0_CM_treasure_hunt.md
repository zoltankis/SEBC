# What is ubertask optimization?
It can be defined in mapreduce.job.ubertask.enable property. It runs small jobs sequentially within a single JVM
# Where in CM is the Kerberos Security Realm value displayed?
In the addministration menu under the settings tab and "Kerberos" category. 
# Which CDH service(s) host a property for enabling Kerberos authentication?
HDFS, MapReduce, YARN, Accumulo, Flume, HBase, Hive, Hue, Impala, Oozie, Pig, Search, Sentry, Spark, Sqoop, Sqoop2, Zookeeper, Cloudera Manager
# How do you upgrade the CM agents?
Before upgrading CM agents I upgrade the CM server with sudo yum update cloudera-manager-server.
After that it can be updated at the Cloudera Manager with the Upgrade Wizard. (for example at Hosts with the "Re-run Upgrade Wizard" button )
# Give the tsquery statement used to chart Hue's CPU utilization?
select cpu_system_rate + cpu_user_rate where category=ROLE and serviceName=Hue
# Name all the roles that make up the Hive service
Hive Metastore Server, HiveServer2, Gateway, WebHCat Server
# What steps must be completed before integrating Cloudera Manager with Kerberos?
- Install a KDC (MIT KD or Acive Directory): openldap-clients on the Cloudera Manager Server host and krb5-workstation, krb5-libs on ALL hosts
- Configure KDC (It should allow renewable tickets with a non zero lifetime)
- If you integrate with AD LDAPS should be enabled Domain Controllers
- In Cloudera Manager there should be an account which has the permissions to create accounts in the KDC