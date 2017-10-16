# Check vm.swappiness on all your nodes
```
[root@ip-172-32-11-139 ~]# for i in $(cat hosts); do ssh -i BigDataSEBCkey.pem centos@$i "hostname -a;cat /proc/sys/vm/swappiness;cat /etc/sysctl.conf | grep swappines"; done
node0
1
vm.swappiness = 1
node1
1
vm.swappiness = 1
node2
1
vm.swappiness = 1
node3
1
vm.swappiness = 1
node4
1
vm.swappiness = 1
```

# Show the mount attributes of all volumes: 
I increased the size of the volumes one every intances:
```
fdisk /dev/xvda
```
After a reboot:
```
[root@ip-172-32-11-139 ~]# for i in $(cat hosts); do ssh -i BigDataSEBCkey.pem centos@$i "hostname -a; lsblk"; done
node0
NAME    MAJ:MIN RM SIZE RO TYPE MOUNTPOINT
xvda    202:0    0  50G  0 disk
└─xvda1 202:1    0  50G  0 part /
node1
NAME    MAJ:MIN RM SIZE RO TYPE MOUNTPOINT
xvda    202:0    0  50G  0 disk
└─xvda1 202:1    0  50G  0 part /
node2
NAME    MAJ:MIN RM SIZE RO TYPE MOUNTPOINT
xvda    202:0    0  50G  0 disk
└─xvda1 202:1    0  50G  0 part /
node3
NAME    MAJ:MIN RM SIZE RO TYPE MOUNTPOINT
xvda    202:0    0  50G  0 disk
└─xvda1 202:1    0  50G  0 part /
node4
NAME    MAJ:MIN RM SIZE RO TYPE MOUNTPOINT
xvda    202:0    0  50G  0 disk
└─xvda1 202:1    0  50G  0 part /
```

# Show the reserve space of any non-root, ext-based volumes:
```
[root@ip-172-32-11-139 ~]# for i in $(cat hosts); do ssh -i BigDataSEBCkey.pem centos@$i "hostname -a; df -h"; done
node0
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       50G  721M   46G   2% /
tmpfs           7.3G     0  7.3G   0% /dev/shm
node1
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       50G  721M   46G   2% /
tmpfs           7.3G     0  7.3G   0% /dev/shm
node2
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       50G  721M   46G   2% /
tmpfs           7.3G     0  7.3G   0% /dev/shm
node3
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       50G  721M   46G   2% /
tmpfs           7.3G     0  7.3G   0% /dev/shm
node4
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       50G  721M   46G   2% /
tmpfs           7.3G     0  7.3G   0% /dev/shm
```

# Disable transparent hugepage support:
Used the following commands on all hosts:
```
echo never > /sys/kernel/mm/transparent_hugepage/defrag
echo never > /sys/kernel/mm/transparent_hugepage/enabled
```
Check transparent huge page:
```
[root@ip-172-32-11-139 ~]# for i in $(cat hosts); do ssh -i BigDataSEBCkey.pem centos@$i "hostname -a;cat /sys/kernel/mm/transparent_hugepage/defrag; cat /sys/kernel/mm/transparent_hugepage/enabled"; done
node0
always madvise [never]
always madvise [never]
node1
always madvise [never]
always madvise [never]
node2
always madvise [never]
always madvise [never]
node3
always madvise [never]
always madvise [never]
node4
always madvise [never]
always madvise [never]
```

# List your network interface configuration
```
[root@ip-172-32-11-139 ~]# for i in $(cat hosts); do ssh -i BigDataSEBCkey.pem centos@$i "hostname -a; /sbin/ip addr"; done
node0
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 9001 qdisc pfifo_fast state UP qlen 1000
    link/ether 02:56:8d:a9:d6:74 brd ff:ff:ff:ff:ff:ff
    inet 172.32.11.139/20 brd 172.32.15.255 scope global eth0
    inet6 fe80::56:8dff:fea9:d674/64 scope link
       valid_lft forever preferred_lft forever
node1
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 9001 qdisc pfifo_fast state UP qlen 1000
    link/ether 02:b9:a9:ba:94:2a brd ff:ff:ff:ff:ff:ff
    inet 172.32.6.254/20 brd 172.32.15.255 scope global eth0
    inet6 fe80::b9:a9ff:feba:942a/64 scope link
       valid_lft forever preferred_lft forever
node2
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 9001 qdisc pfifo_fast state UP qlen 1000
    link/ether 02:2f:bd:8c:82:8e brd ff:ff:ff:ff:ff:ff
    inet 172.32.13.168/20 brd 172.32.15.255 scope global eth0
    inet6 fe80::2f:bdff:fe8c:828e/64 scope link
       valid_lft forever preferred_lft forever
node3
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 9001 qdisc pfifo_fast state UP qlen 1000
    link/ether 02:8c:5e:3b:9e:98 brd ff:ff:ff:ff:ff:ff
    inet 172.32.6.238/20 brd 172.32.15.255 scope global eth0
    inet6 fe80::8c:5eff:fe3b:9e98/64 scope link
       valid_lft forever preferred_lft forever
node4
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 9001 qdisc pfifo_fast state UP qlen 1000
    link/ether 02:de:cb:94:ff:10 brd ff:ff:ff:ff:ff:ff
    inet 172.32.6.75/20 brd 172.32.15.255 scope global eth0
    inet6 fe80::de:cbff:fe94:ff10/64 scope link
       valid_lft forever preferred_lft forever
```

# List forward and reverse host lookups using getent or nslookup
```
[root@ip-172-32-11-139 ~]# COMMAND="hostname -a; getent hosts $HOSTS"; HOSTS="node0 node1 node2 node3 node4"; for i in $HOSTS; do ssh -i BigDataSEBCkey.pem centos@$i $COMMAND; done
node0
172.32.11.139   ip-172-32-11-139.eu-central-1.compute.internal node0
172.32.6.254    ip-172-32-6-254.eu-central-1.compute.internal node1
172.32.13.168   ip-172-32-13-168.eu-central-1.compute.internal node2
172.32.6.238    ip-172-32-6-238.eu-central-1.compute.internal node3
172.32.6.75     ip-172-32-6-75.eu-central-1.compute.internal node4
node1
172.32.11.139   ip-172-32-11-139.eu-central-1.compute.internal node0
172.32.6.254    ip-172-32-6-254.eu-central-1.compute.internal node1
172.32.13.168   ip-172-32-13-168.eu-central-1.compute.internal node2
172.32.6.238    ip-172-32-6-238.eu-central-1.compute.internal node3
172.32.6.75     ip-172-32-6-75.eu-central-1.compute.internal node4
node2
172.32.11.139   ip-172-32-11-139.eu-central-1.compute.internal node0
172.32.6.254    ip-172-32-6-254.eu-central-1.compute.internal node1
172.32.13.168   ip-172-32-13-168.eu-central-1.compute.internal node2
172.32.6.238    ip-172-32-6-238.eu-central-1.compute.internal node3
172.32.6.75     ip-172-32-6-75.eu-central-1.compute.internal node4
node3
172.32.11.139   ip-172-32-11-139.eu-central-1.compute.internal node0
172.32.6.254    ip-172-32-6-254.eu-central-1.compute.internal node1
172.32.13.168   ip-172-32-13-168.eu-central-1.compute.internal node2
172.32.6.238    ip-172-32-6-238.eu-central-1.compute.internal node3
172.32.6.75     ip-172-32-6-75.eu-central-1.compute.internal node4
node4
172.32.11.139   ip-172-32-11-139.eu-central-1.compute.internal node0
172.32.6.254    ip-172-32-6-254.eu-central-1.compute.internal node1
172.32.13.168   ip-172-32-13-168.eu-central-1.compute.internal node2
172.32.6.238    ip-172-32-6-238.eu-central-1.compute.internal node3
172.32.6.75     ip-172-32-6-75.eu-central-1.compute.internal node4
```

# Show the nscd service is running
Install nsd and ntp on all hosts:
```
yum install -y nscd ntp
```
Start NSCD on all hosts
```
for i in $(cat hosts); do ssh -i BigDataSEBCkey.pem centos@$i "hostname -a; sudo /sbin/service nscd start"; done
node0
Starting nscd: [  OK  ]
node1
Starting nscd: [  OK  ]
node2
Starting nscd: [  OK  ]
node3
Starting nscd: [  OK  ]
node4
Starting nscd: [  OK  ]
```
NSCD status on all hosts:
```
[root@ip-172-32-11-139 ~]# for i in $(cat hosts); do ssh -i BigDataSEBCkey.pem centos@$i "hostname -a; /sbin/service nscd status"; done

node0
nscd (pid 2279) is running...
node1
nscd (pid 2123) is running...
node2
nscd (pid 1997) is running...
node3
nscd (pid 1986) is running...
node4
nscd (pid 1972) is running...
```
# Show the ntpd service is running
Start NTPD on all hosts
```
for i in $(cat hosts); do ssh -i BigDataSEBCkey.pem centos@$i "hostname -a; sudo /sbin/service ntpd start"; done
node0
Starting ntpd: [  OK  ]
node1
Starting ntpd: [  OK  ]
node2
Starting ntpd: [  OK  ]
node3
Starting ntpd: [  OK  ]
node4
Starting ntpd: [  OK  ]
```

NTPD status on all hosts:
```
[root@ip-172-32-11-139 ~]# for i in $(cat hosts); do ssh -i BigDataSEBCkey.pem centos@$i "hostname -a; /sbin/service ntpd status"; done
node0
ntpd (pid  2357) is running...
node1
ntpd (pid  2187) is running...
node2
ntpd (pid  2061) is running...
node3
ntpd (pid  2050) is running...
node4
ntpd (pid  2036) is running...
```
