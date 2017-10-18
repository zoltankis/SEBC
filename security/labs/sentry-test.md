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
# Create a Sentry role with full authorization
```
0: jdbc:hive2://localhost:10000/default> CREATE ROLE sentry_admin;
INFO  : Compiling command(queryId=hive_20171018211919_5da69551-88a6-445f-8c6b-1402c96434eb):                                                                                                                          CREATE ROLE sentry_admin
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171018211919_5da69551-88a6-445f-8c6b-1402c                                                                                                                         96434eb); Time taken: 0.067 seconds
INFO  : Executing command(queryId=hive_20171018211919_5da69551-88a6-445f-8c6b-1402c96434eb):                                                                                                                          CREATE ROLE sentry_admin
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171018211919_5da69551-88a6-445f-8c6b-1402c                                                                                                                         96434eb); Time taken: 0.714 seconds
INFO  : OK
No rows affected (0.8 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT ALL ON SERVER server1 TO ROLE sentry_admin;
INFO  : Compiling command(queryId=hive_20171018211919_6457c674-efa0-45ca-a612-3b37a381be91):                                                                                                                          GRANT ALL ON SERVER server1 TO ROLE sentry_admin
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171018211919_6457c674-efa0-45ca-a612-3b37a                                                                                                                         381be91); Time taken: 0.115 seconds
INFO  : Executing command(queryId=hive_20171018211919_6457c674-efa0-45ca-a612-3b37a381be91):                                                                                                                          GRANT ALL ON SERVER server1 TO ROLE sentry_admin
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171018211919_6457c674-efa0-45ca-a612-3b37a                                                                                                                         381be91); Time taken: 0.079 seconds
INFO  : OK
No rows affected (0.207 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT ROLE sentry_admin TO GROUP sebc;
INFO  : Compiling command(queryId=hive_20171018211919_bf4b1b6e-7ee0-4bba-ae98-b1d340d559ca):                                                                                                                          GRANT ROLE sentry_admin TO GROUP sebc
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171018211919_bf4b1b6e-7ee0-4bba-ae98-b1d34                                                                                                                         0d559ca); Time taken: 0.071 seconds
INFO  : Executing command(queryId=hive_20171018211919_bf4b1b6e-7ee0-4bba-ae98-b1d340d559ca):                                                                                                                          GRANT ROLE sentry_admin TO GROUP sebc
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171018211919_bf4b1b6e-7ee0-4bba-ae98-b1d34                                                                                                                         0d559ca); Time taken: 0.066 seconds
INFO  : OK
No rows affected (0.15 seconds)
0: jdbc:hive2://localhost:10000/default> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20171018211919_38ede2ec-4d3c-4c2a-a438-f48ab37acd02):                                                                                                                          SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, c                                                                                                                         omment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171018211919_38ede2ec-4d3c-4c2a-a438-f48ab                                                                                                                         37acd02); Time taken: 0.074 seconds
INFO  : Executing command(queryId=hive_20171018211919_38ede2ec-4d3c-4c2a-a438-f48ab37acd02):                                                                                                                          SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171018211919_38ede2ec-4d3c-4c2a-a438-f48ab                                                                                                                         37acd02); Time taken: 0.134 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
```
# Create additional test users
```
[root@ip-172-32-11-139 ~]# COMMAND="sudo groupadd selector"; \
> HOSTS="node0 node1 node2 node3 node4"; \
> for i in $HOSTS; do ssh -i BigDataSEBCkey.pem centos@$i $COMMAND; done
[root@ip-172-32-11-139 ~]# COMMAND="sudo groupadd inserters"; \
> HOSTS="node0 node1 node2 node3 node4"; \
> for i in $HOSTS; do ssh -i BigDataSEBCkey.pem centos@$i $COMMAND; done
[root@ip-172-32-11-139 ~]# COMMAND="sudo useradd -u 1100 -g selector george"; \
> HOSTS="node0 node1 node2 node3 node4"; \
> for i in $HOSTS; do ssh -i BigDataSEBCkey.pem centos@$i $COMMAND; done
[root@ip-172-32-11-139 ~]# COMMAND="sudo useradd -u 1200 -g inserters ferdinand"; \
> HOSTS="node0 node1 node2 node3 node4"; \
> for i in $HOSTS; do ssh -i BigDataSEBCkey.pem centos@$i $COMMAND; done
[root@ip-172-32-11-139 ~]# ssh -i BigDataSEBCkey.pem centos@node1
```
# Create test roles
```
0: jdbc:hive2://localhost:10000/default> CREATE ROLE reads;
INFO  : Compiling command(queryId=hive_20171018212222_9be2d9cc-15bd-4e6a-8f25-f58bf1bd7793):                                                                                                                          CREATE ROLE reads
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171018212222_9be2d9cc-15bd-4e6a-8f25-f58bf                                                                                                                         1bd7793); Time taken: 0.063 seconds
INFO  : Executing command(queryId=hive_20171018212222_9be2d9cc-15bd-4e6a-8f25-f58bf1bd7793):                                                                                                                          CREATE ROLE reads
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171018212222_9be2d9cc-15bd-4e6a-8f25-f58bf                                                                                                                         1bd7793); Time taken: 0.025 seconds
INFO  : OK
No rows affected (0.101 seconds)
0: jdbc:hive2://localhost:10000/default> CREATE ROLE writes;
INFO  : Compiling command(queryId=hive_20171018212222_38846e6f-a713-4ca9-9a8a-f38346bc43c0):                                                                                                                          CREATE ROLE writes
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171018212222_38846e6f-a713-4ca9-9a8a-f3834                                                                                                                         6bc43c0); Time taken: 0.063 seconds
INFO  : Executing command(queryId=hive_20171018212222_38846e6f-a713-4ca9-9a8a-f38346bc43c0):                                                                                                                          CREATE ROLE writes
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171018212222_38846e6f-a713-4ca9-9a8a-f3834                                                                                                                         6bc43c0); Time taken: 0.025 seconds
INFO  : OK
No rows affected (0.102 seconds)
```
# Grant read privilege for all tables to reads
```
0: jdbc:hive2://localhost:10000/default> GRANT SELECT ON DATABASE default TO ROLE reads;
INFO  : Compiling command(queryId=hive_20171018212323_43d5cbab-a933-4caa-8919-b0e1101ece7c):                                                                                                                          GRANT SELECT ON DATABASE default TO ROLE reads
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171018212323_43d5cbab-a933-4caa-8919-b0e11                                                                                                                         01ece7c); Time taken: 0.053 seconds
INFO  : Executing command(queryId=hive_20171018212323_43d5cbab-a933-4caa-8919-b0e1101ece7c):                                                                                                                          GRANT SELECT ON DATABASE default TO ROLE reads
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171018212323_43d5cbab-a933-4caa-8919-b0e11                                                                                                                         01ece7c); Time taken: 0.036 seconds
INFO  : OK
No rows affected (0.102 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT ROLE reads TO GROUP selector;
INFO  : Compiling command(queryId=hive_20171018212323_83e468a3-b3a8-4133-a3fc-9cb6b14f7e73):                                                                                                                          GRANT ROLE reads TO GROUP selector
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171018212323_83e468a3-b3a8-4133-a3fc-9cb6b                                                                                                                         14f7e73); Time taken: 0.057 seconds
INFO  : Executing command(queryId=hive_20171018212323_83e468a3-b3a8-4133-a3fc-9cb6b14f7e73):                                                                                                                          GRANT ROLE reads TO GROUP selector
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171018212323_83e468a3-b3a8-4133-a3fc-9cb6b                                                                                                                         14f7e73); Time taken: 0.03 seconds
INFO  : OK
No rows affected (0.099 seconds)
```
# Grant read privilege for default.sample07 only to 'writes':
```
0: jdbc:hive2://localhost:10000/default> REVOKE ALL ON DATABASE default FROM ROLE writes;
INFO  : Compiling command(queryId=hive_20171018212323_ee42e37c-49bd-42b6-840b-5bef181948fc):                                                                                                                          REVOKE ALL ON DATABASE default FROM ROLE writes
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171018212323_ee42e37c-49bd-42b6-840b-5bef1                                                                                                                         81948fc); Time taken: 0.072 seconds
INFO  : Executing command(queryId=hive_20171018212323_ee42e37c-49bd-42b6-840b-5bef181948fc):                                                                                                                          REVOKE ALL ON DATABASE default FROM ROLE writes
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171018212323_ee42e37c-49bd-42b6-840b-5bef1                                                                                                                         81948fc); Time taken: 0.085 seconds
INFO  : OK
No rows affected (0.18 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT SELECT ON default.sample_07 TO ROLE writes;
INFO  : Compiling command(queryId=hive_20171018212323_ac66ce16-f6a7-4bf5-b59f-9461de3cf9dd):                                                                                                                          GRANT SELECT ON default.sample_07 TO ROLE writes
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171018212323_ac66ce16-f6a7-4bf5-b59f-9461d                                                                                                                         e3cf9dd); Time taken: 0.056 seconds
INFO  : Executing command(queryId=hive_20171018212323_ac66ce16-f6a7-4bf5-b59f-9461de3cf9dd):                                                                                                                          GRANT SELECT ON default.sample_07 TO ROLE writes
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171018212323_ac66ce16-f6a7-4bf5-b59f-9461d                                                                                                                         e3cf9dd); Time taken: 0.034 seconds
INFO  : OK
No rows affected (0.104 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT ROLE writes TO GROUP inserters;
INFO  : Compiling command(queryId=hive_20171018212323_e71cd81f-397b-49fb-8e61-77b105725d22):                                                                                                                          GRANT ROLE writes TO GROUP inserters
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171018212323_e71cd81f-397b-49fb-8e61-77b10                                                                                                                         5725d22); Time taken: 0.062 seconds
INFO  : Executing command(queryId=hive_20171018212323_e71cd81f-397b-49fb-8e61-77b105725d22):                                                                                                                          GRANT ROLE writes TO GROUP inserters
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171018212323_e71cd81f-397b-49fb-8e61-77b10                                                                                                                         5725d22); Time taken: 0.026 seconds
INFO  : OK
No rows affected (0.101 seconds)
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
# kinit as ferdinand, then login to beeline
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
