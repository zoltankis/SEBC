# The hostname of your MySQL node
```
[root@ip-172-32-1-58 ~]# hostname -f
ip-172-32-1-58.eu-central-1.compute.internal
```

# The command and output for mysql --version
```
[root@ip-172-32-1-58 ~]# mysql --version
mysql  Ver 14.14 Distrib 5.5.58, for Linux (x86_64) using readline 5.1
```

# The command and output for listing MySQL databases
```
[root@ip-172-32-1-58 ~]# mysql -u root -p
Enter password:
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 11
Server version: 5.5.58 MySQL Community Server (GPL)

Copyright (c) 2000, 2017, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| hive               |
| hue                |
| mysql              |
| oozie              |
| performance_schema |
| rman               |
| scm                |
| sentry             |
+--------------------+
9 rows in set (0.00 sec)

mysql>
```