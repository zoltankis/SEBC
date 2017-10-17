# Browse the results
Teragen local result:
```
[root@ip-172-32-11-139 ~]# sudo -u hdfs hdfs fsck /user/zoltankis/ex1_zoltankis_source -files -blocks
Connecting to namenode via http://ip-172-32-6-254.eu-central-1.compute.internal:50070
FSCK started by hdfs (auth:SIMPLE) from /172.32.11.139 for path /user/zoltankis/ex1_zoltankis_source at Tue Oct 17 09:05:49 UTC 2017
/user/zoltankis/ex1_zoltankis_source <dir>
/user/zoltankis/ex1_zoltankis_source/_SUCCESS 0 bytes, 0 block(s):  OK

/user/zoltankis/ex1_zoltankis_source/part-m-00000 524288000 bytes, 4 block(s):  OK
0. BP-897431355-172.32.6.254-1508192624786:blk_1073743413_2589 len=134217728 Live_repl=3
1. BP-897431355-172.32.6.254-1508192624786:blk_1073743414_2590 len=134217728 Live_repl=3
2. BP-897431355-172.32.6.254-1508192624786:blk_1073743415_2591 len=134217728 Live_repl=3
3. BP-897431355-172.32.6.254-1508192624786:blk_1073743416_2592 len=121634816 Live_repl=3

Status: HEALTHY
 Total size:    524288000 B
 Total dirs:    1
 Total files:   2
 Total symlinks:                0
 Total blocks (validated):      4 (avg. block size 131072000 B)
 Minimally replicated blocks:   4 (100.0 %)
 Over-replicated blocks:        0 (0.0 %)
 Under-replicated blocks:       0 (0.0 %)
 Mis-replicated blocks:         0 (0.0 %)
 Default replication factor:    3
 Average block replication:     3.0
 Corrupt blocks:                0
 Missing replicas:              0 (0.0 %)
 Number of data-nodes:          4
 Number of racks:               1
FSCK ended at Tue Oct 17 09:05:49 UTC 2017 in 1 milliseconds


The filesystem under path '/user/zoltankis/ex1_zoltankis_source' is HEALTHY
```

Teragen result from user amakoviczki:

```
[root@ip-172-32-11-139 ~]# sudo -u hdfs hdfs fsck /user/zoltankis/ex1_andrasmakoviczki_target -files -blocks
Connecting to namenode via http://ip-172-32-6-254.eu-central-1.compute.internal:50070
FSCK started by hdfs (auth:SIMPLE) from /172.32.11.139 for path /user/zoltankis/ex1_andrasmakoviczki_target at Tue Oct 17 09:07:48 UTC 2017
/user/zoltankis/ex1_andrasmakoviczki_target <dir>
/user/zoltankis/ex1_andrasmakoviczki_target/ex1_andrasmakoviczki_source <dir>
/user/zoltankis/ex1_andrasmakoviczki_target/ex1_andrasmakoviczki_source/_SUCCESS 0 bytes, 0 block(s):  OK

/user/zoltankis/ex1_andrasmakoviczki_target/ex1_andrasmakoviczki_source/part-m-00000 262144000 bytes, 2 block(s):  OK
0. BP-897431355-172.32.6.254-1508192624786:blk_1073743477_2653 len=134217728 Live_repl=3
1. BP-897431355-172.32.6.254-1508192624786:blk_1073743478_2654 len=127926272 Live_repl=3

/user/zoltankis/ex1_andrasmakoviczki_target/ex1_andrasmakoviczki_source/part-m-00001 262144000 bytes, 2 block(s):  OK
0. BP-897431355-172.32.6.254-1508192624786:blk_1073743479_2655 len=134217728 Live_repl=3
1. BP-897431355-172.32.6.254-1508192624786:blk_1073743480_2656 len=127926272 Live_repl=3

Status: HEALTHY
 Total size:    524288000 B
 Total dirs:    2
 Total files:   3
 Total symlinks:                0
 Total blocks (validated):      4 (avg. block size 131072000 B)
 Minimally replicated blocks:   4 (100.0 %)
 Over-replicated blocks:        0 (0.0 %)
 Under-replicated blocks:       0 (0.0 %)
 Mis-replicated blocks:         0 (0.0 %)
 Default replication factor:    3
 Average block replication:     3.0
 Corrupt blocks:                0
 Missing replicas:              0 (0.0 %)
 Number of data-nodes:          4
 Number of racks:               1
FSCK ended at Tue Oct 17 09:07:48 UTC 2017 in 1 milliseconds


The filesystem under path '/user/zoltankis/ex1_andrasmakoviczki_target' is HEALTHY
```