Check vm.swappiness on all your nodes
```
[root@ip-172-32-11-139 ~]# for i in $(cat hosts); do ssh -i BigDataSEBCkey.pem centos@$i hostname -a;cat /proc/sys/vm/swappiness;cat /etc/sysctl.conf | grep swappines; done
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

Show the mount attributes of all volumes: 
I increased the size of the volumes one every intances:
```
fdisk /dev/xvda
```
After a reboot:
```
[root@ip-172-32-11-139 ~]# for i in $(cat hosts); do ssh -i BigDataSEBCkey.pem centos@$i hostname -a; lsblk; done
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

Show the reserve space of any non-root, ext-based volumes:
```
[root@ip-172-32-11-139 ~]# for i in $(cat hosts); do ssh -i BigDataSEBCkey.pem centos@$i hostname -a; df -h; done
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

