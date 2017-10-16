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