# Cloud Provider
AWS

# Linux release
```
[root@ip-172-32-1-58 ~]# cat /proc/version
Linux version 2.6.32-696.1.1.el6.x86_64 (mockbuild@c1bm.rdu2.centos.org) (gcc version 4.4.7 20120313 (Red Hat 4.4.7-18) (GCC) ) #1 SMP Tue Apr 11 17:13:24 UTC 2017
```

# Disk space on each node is at least 30 GB
```
[root@ip-172-32-1-58 ~]# COMMAND="df -h"; \
> HOSTS="node0 node1 node2 node3 node4"; \
> for i in $HOSTS; do ssh -i BigDataSEBCkey.pem centos@$i $COMMAND; done
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       50G  876M   46G   2% /
tmpfs           7.3G     0  7.3G   0% /dev/shm
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       50G  876M   46G   2% /
tmpfs           7.3G     0  7.3G   0% /dev/shm
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       50G  876M   46G   2% /
tmpfs           7.3G     0  7.3G   0% /dev/shm
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       50G  876M   46G   2% /
tmpfs           7.3G     0  7.3G   0% /dev/shm
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       50G  876M   46G   2% /
tmpfs           7.3G     0  7.3G   0% /dev/shm
```


# yum repolist enabled
```
[root@ip-172-32-1-58 ~]# COMMAND="yum repolist enabled"; \
> HOSTS="node0 node1 node2 node3 node4"; \
> for i in $HOSTS; do ssh -i BigDataSEBCkey.pem centos@$i $COMMAND; done
Loaded plugins: fastestmirror, presto
Determining fastest mirrors
 * base: mirror.fra10.de.leaseweb.net
 * extras: mirror.imt-systems.com
 * updates: mirror.imt-systems.com
repo id                        repo name                                  status
base                           CentOS-6 - Base                            6,706
extras                         CentOS-6 - Extras                             46
updates                        CentOS-6 - Updates                           723
repolist: 7,475
Loaded plugins: fastestmirror, presto
Determining fastest mirrors
 * base: mirror.fra10.de.leaseweb.net
 * extras: mirror.imt-systems.com
 * updates: mirror.imt-systems.com
repo id                        repo name                                  status
base                           CentOS-6 - Base                            6,706
extras                         CentOS-6 - Extras                             46
updates                        CentOS-6 - Updates                           723
repolist: 7,475
Loaded plugins: fastestmirror, presto
Determining fastest mirrors
 * base: mirror.fra10.de.leaseweb.net
 * extras: mirror.imt-systems.com
 * updates: mirror.imt-systems.com
repo id                        repo name                                  status
base                           CentOS-6 - Base                            6,706
extras                         CentOS-6 - Extras                             46
updates                        CentOS-6 - Updates                           723
repolist: 7,475
Loaded plugins: fastestmirror, presto
Determining fastest mirrors
 * base: mirror.fra10.de.leaseweb.net
 * extras: mirror.imt-systems.com
 * updates: mirror.imt-systems.com
repo id                        repo name                                  status
base                           CentOS-6 - Base                            6,706
extras                         CentOS-6 - Extras                             46
updates                        CentOS-6 - Updates                           723
repolist: 7,475
Loaded plugins: fastestmirror, presto
Determining fastest mirrors
 * base: mirror.fra10.de.leaseweb.net
 * extras: mirror.imt-systems.com
 * updates: mirror.imt-systems.com
repo id                        repo name                                  status
base                           CentOS-6 - Base                            6,706
extras                         CentOS-6 - Extras                             46
updates                        CentOS-6 - Updates                           723
repolist: 7,475
```
# List the /etc/passwd entries for ernest and siwicki
```
[root@ip-172-32-1-58 ~]# COMMAND="sudo cat /etc/passwd | grep \"ernest\|siwicki\""; \
> HOSTS="node0 node1 node2 node3 node4"; \
> for i in $HOSTS; do ssh -i BigDataSEBCkey.pem centos@$i $COMMAND; done
ernest:x:2000:3001::/home/ernest:/bin/bash
siwicki:x:3000:3002::/home/siwicki:/bin/bash
ernest:x:2000:3001::/home/ernest:/bin/bash
siwicki:x:3000:3002::/home/siwicki:/bin/bash
ernest:x:2000:3001::/home/ernest:/bin/bash
siwicki:x:3000:3002::/home/siwicki:/bin/bash
ernest:x:2000:3001::/home/ernest:/bin/bash
siwicki:x:3000:3002::/home/siwicki:/bin/bash
ernest:x:2000:3001::/home/ernest:/bin/bash
siwicki:x:3000:3002::/home/siwicki:/bin/bash
```
# List the /etc/group entries for usa and emea
```
[root@ip-172-32-1-58 ~]# COMMAND="sudo cat /etc/group | grep \"usa\|emea\""; \
> HOSTS="node0 node1 node2 node3 node4"; \
> for i in $HOSTS; do ssh -i BigDataSEBCkey.pem centos@$i $COMMAND; done
usa:x:3001:ernest
emea:x:3002:siwicki
usa:x:3001:ernest
emea:x:3002:siwicki
usa:x:3001:ernest
emea:x:3002:siwicki
usa:x:3001:ernest
emea:x:3002:siwicki
usa:x:3001:ernest
emea:x:3002:siwicki
```
