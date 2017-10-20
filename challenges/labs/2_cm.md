# List the command and output of ls /etc/yum.repos.d
```
[root@ip-172-32-1-58 ~]# ls /etc/yum.repos.d
CentOS-Base.repo       CentOS-fasttrack.repo  CentOS-Vault.repo      mysql-community.repo
CentOS-Debuginfo.repo  CentOS-Media.repo      cloudera-manager.repo
```
# List the full command line of
```
[root@ip-172-32-9-114 ~]# /usr/share/cmf/schema/scm_prepare_database.sh mysql scm scm -p -h 1                                                                                                                         72.32.1.58 -P 3306
Enter database password:
Enter SCM password:
JAVA_HOME=/usr/java/jre1.8.0_131
Verifying that we can write to /etc/cloudera-scm-server
Creating SCM configuration file in /etc/cloudera-scm-server
Executing:  /usr/java/jre1.8.0_131/bin/java -cp /usr/share/java/mysql-connector-java.jar:/usr                                                                                                                         /share/java/oracle-connector-java.jar:/usr/share/cmf/schema/../lib/* com.cloudera.enterprise.                                                                                                                         dbutil.DbCommandExecutor /etc/cloudera-scm-server/db.properties com.cloudera.cmf.db.
[                          main] DbCommandExecutor              INFO  Successfully connected                                                                                                                          to database.
All done, your SCM database is configured correctly!
[root@ip-172-32-9-114 ~]#
```