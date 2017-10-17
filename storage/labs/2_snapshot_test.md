# Test HDFS Snapshots
```
[centos@ip-172-32-6-254 ~]$ sudo -u hdfs hdfs dfs -copyFromLocal /tmp/SEBC-master.zip /precious/
[centos@ip-172-32-6-254 ~]$ sudo -u hdfs hdfs dfsadmin -allowSnapshot /precious/
Allowing snaphot on /precious/ succeeded
[centos@ip-172-32-6-254 ~]$ sudo -u hdfs hdfs dfs -createSnapshot /precious/ sebc-hdfs-test
Created snapshot /precious/.snapshot/sebc-hdfs-test
[centos@ip-172-32-6-254 ~]$ sudo -u hdfs hdfs dfs -rm -R /precious
rm: Failed to move to trash: hdfs://ip-172-32-6-254.eu-central-1.compute.internal:8020/precious: The directory /precious cannot be deleted since /precious is snapshottable and already has snapshots
[centos@ip-172-32-6-254 ~]$ sudo -u hdfs hdfs dfs -rm -R /precious/*
17/10/17 11:59:49 INFO fs.TrashPolicyDefault: Moved: 'hdfs://ip-172-32-6-254.eu-central-1.compute.internal:8020/precious/SEBC-master.zip' to trash at: hdfs://ip-172-32-6-254.eu-central-1.compute.internal:8020/user/hdfs/.Trash/Current/precious/SEBC-master.zip
[centos@ip-172-32-6-254 ~]$ sudo -u hdfs hdfs dfs -cp /precious/.snapshot/sebc-hdfs-test /precious/
[centos@ip-172-32-6-254 ~]$ sudo -u hdfs hdfs dfs -ls /precious/
Found 1 items
drwxr-xr-x   - hdfs supergroup          0 2017-10-17 12:07 /precious/sebc-hdfs-test
```