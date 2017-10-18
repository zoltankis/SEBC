# Verify user privileges
```
[centos@ip-172-32-6-254 ~]$ kinit zoltankis
Password for zoltankis@COMPUTE.INTERNAL:
[centos@ip-172-32-6-254 ~]$ beeline
Beeline version 1.1.0-cdh5.9.3 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-32-6-254.eu-central-1.compute.internal@COMPUTE.INTERNAL
scan complete in 2ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-32-6-254.eu-central-1.compute.internal@COMPUTE.INTERNAL
Connected to: Apache Hive (version 1.1.0-cdh5.9.3)
Driver: Hive JDBC (version 1.1.0-cdh5.9.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default>
0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20171018211717_f89d4adf-775d-40e0-aa32-c949640c994a): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171018211717_f89d4adf-775d-40e0-aa32-c949640c994a); Time taken: 0.67 seconds
INFO  : Executing command(queryId=hive_20171018211717_f89d4adf-775d-40e0-aa32-c949640c994a): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171018211717_f89d4adf-775d-40e0-aa32-c949640c994a); Time taken: 0.276 seconds
INFO  : OK
+-----------+--+
| tab_name  |
+-----------+--+
+-----------+--+
No rows selected (1.274 seconds)
```
# kinit as george, then login to beeline
```
[centos@ip-172-32-6-254 ~]$ kinit george
Password for george@COMPUTE.INTERNAL:
[centos@ip-172-32-6-254 ~]$ beeline
Beeline version 1.1.0-cdh5.9.3 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-32-6-254.eu-central-1.compute.internal@COMPUTE.INTERNAL
scan complete in 2ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-32-6-254.eu-central-1.compute.internal@COMPUTE.INTERNAL
Connected to: Apache Hive (version 1.1.0-cdh5.9.3)
Driver: Hive JDBC (version 1.1.0-cdh5.9.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20171018212525_670968b8-0620-404f-8c48-a7baba6cfc49): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171018212525_670968b8-0620-404f-8c48-a7baba6cfc49); Time taken: 0.066 seconds
INFO  : Executing command(queryId=hive_20171018212525_670968b8-0620-404f-8c48-a7baba6cfc49): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171018212525_670968b8-0620-404f-8c48-a7baba6cfc49); Time taken: 0.123 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.284 seconds)

```
# kinit as george, then login to beeline
```
[centos@ip-172-32-6-254 ~]$ kinit ferdinand
Password for ferdinand@COMPUTE.INTERNAL:
[centos@ip-172-32-6-254 ~]$ beeline
Beeline version 1.1.0-cdh5.9.3 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-32-6-254.eu-central-1.compute.internal@COMPUTE.INTERNAL
scan complete in 2ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-32-6-254.eu-central-1.compute.internal@COMPUTE.INTERNAL
Connected to: Apache Hive (version 1.1.0-cdh5.9.3)
Driver: Hive JDBC (version 1.1.0-cdh5.9.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20171018212727_e3c6d921-fb01-4ad5-a8b6-1d0c1c323fda): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171018212727_e3c6d921-fb01-4ad5-a8b6-1d0c1c323fda); Time taken: 0.063 seconds
INFO  : Executing command(queryId=hive_20171018212727_e3c6d921-fb01-4ad5-a8b6-1d0c1c323fda): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171018212727_e3c6d921-fb01-4ad5-a8b6-1d0c1c323fda); Time taken: 0.136 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| sample_07  |
+------------+--+
1 row selected (0.3 seconds)

```
