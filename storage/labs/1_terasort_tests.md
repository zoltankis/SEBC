# Run Teragen with time
```
[root@ip-172-32-6-254 ~]# sudo -u hdfs time yarn jar /opt/cloudera/parcels/CDH/jars/hadoop-examples.jar teragen -Dmapreduce.job.maps=4 -Dmapreduce.map.speculative=false -Ddfs.blocksize=32M 107374182 /user/zoltankis/terasort-input
17/10/17 09:48:46 INFO client.RMProxy: Connecting to ResourceManager at ip-172-32-6-254.eu-central-1.compute.internal/172.32.6.254:8032
17/10/17 09:48:47 INFO terasort.TeraSort: Generating 107374182 using 4
17/10/17 09:48:47 INFO mapreduce.JobSubmitter: number of splits:4
17/10/17 09:48:47 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1508192679065_0001
17/10/17 09:48:48 INFO impl.YarnClientImpl: Submitted application application_1508192679065_0001
17/10/17 09:48:48 INFO mapreduce.Job: The url to track the job: http://ip-172-32-6-254.eu-central-1.compute.internal:8088/proxy/application_1508192679065_0001/
17/10/17 09:48:48 INFO mapreduce.Job: Running job: job_1508192679065_0001
17/10/17 09:48:55 INFO mapreduce.Job: Job job_1508192679065_0001 running in uber mode : false
17/10/17 09:48:55 INFO mapreduce.Job:  map 0% reduce 0%
...
17/10/17 09:50:53 INFO mapreduce.Job:  map 99% reduce 0%
17/10/17 09:50:54 INFO mapreduce.Job:  map 100% reduce 0%
17/10/17 09:50:55 INFO mapreduce.Job: Job job_1508192679065_0001 completed successfully
17/10/17 09:50:55 INFO mapreduce.Job: Counters: 31
        File System Counters
                FILE: Number of bytes read=0
                FILE: Number of bytes written=488544
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=344
                HDFS: Number of bytes written=10737418200
                HDFS: Number of read operations=16
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=8
        Job Counters
                Launched map tasks=4
                Other local map tasks=4
                Total time spent by all maps in occupied slots (ms)=456810
                Total time spent by all reduces in occupied slots (ms)=0
                Total time spent by all map tasks (ms)=456810
                Total vcore-seconds taken by all map tasks=456810
                Total megabyte-seconds taken by all map tasks=467773440
        Map-Reduce Framework
                Map input records=107374182
                Map output records=107374182
                Input split bytes=344
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=1992
                CPU time spent (ms)=158400
                Physical memory (bytes) snapshot=821334016
                Virtual memory (bytes) snapshot=6255378432
                Total committed heap usage (bytes)=848297984
        org.apache.hadoop.examples.terasort.TeraGen$Counters
                CHECKSUM=230593859918397906
        File Input Format Counters
                Bytes Read=0
        File Output Format Counters
                Bytes Written=10737418200
6.03user 0.28system 2:11.22elapsed 4%CPU (0avgtext+0avgdata 183004maxresident)k
3464inputs+1432outputs (2major+37062minor)pagefaults 0swaps
```

# Run Terasort with time

```
[root@ip-172-32-6-254 ~]# sudo -u hdfs time hadoop jar /opt/cloudera/parcels/CDH/jars/hadoop-examples.jar terasort /user/zoltankis/terasort-input /user/zoltankis/terasort-output
17/10/17 09:53:36 INFO terasort.TeraSort: starting
17/10/17 09:53:37 INFO input.FileInputFormat: Total input paths to process : 4
Spent 247ms computing base-splits.
Spent 7ms computing TeraScheduler splits.
Computing input splits took 255ms
Sampling 10 splits of 320
Making 8 from 100000 sampled records
Computing parititions took 915ms
Spent 1173ms computing partitions.
17/10/17 09:53:38 INFO client.RMProxy: Connecting to ResourceManager at ip-172-32-6-254.eu-central-1.compute.internal/172.32.6.254:8032
17/10/17 09:53:38 INFO mapreduce.JobSubmitter: number of splits:320
17/10/17 09:53:39 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1508192679065_0002
17/10/17 09:53:39 INFO impl.YarnClientImpl: Submitted application application_1508192679065_0002
17/10/17 09:53:39 INFO mapreduce.Job: The url to track the job: http://ip-172-32-6-254.eu-central-1.compute.internal:8088/proxy/application_1508192679065_0002/
17/10/17 09:53:39 INFO mapreduce.Job: Running job: job_1508192679065_0002
17/10/17 09:53:44 INFO mapreduce.Job: Job job_1508192679065_0002 running in uber mode : false
17/10/17 09:53:44 INFO mapreduce.Job:  map 0% reduce 0%
...
17/10/17 10:00:26 INFO mapreduce.Job:  map 100% reduce 100%
17/10/17 10:00:28 INFO mapreduce.Job: Job job_1508192679065_0002 completed successfully
17/10/17 10:00:29 INFO mapreduce.Job: Counters: 50
        File System Counters
                FILE: Number of bytes read=4811283555
                FILE: Number of bytes written=9549442798
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=10737471000
                HDFS: Number of bytes written=10737418200
                HDFS: Number of read operations=984
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=16
        Job Counters
                Launched map tasks=320
                Launched reduce tasks=8
                Data-local map tasks=313
                Rack-local map tasks=7
                Total time spent by all maps in occupied slots (ms)=2272507
                Total time spent by all reduces in occupied slots (ms)=876711
                Total time spent by all map tasks (ms)=2272507
                Total time spent by all reduce tasks (ms)=876711
                Total vcore-seconds taken by all map tasks=2272507
                Total vcore-seconds taken by all reduce tasks=876711
                Total megabyte-seconds taken by all map tasks=2327047168
                Total megabyte-seconds taken by all reduce tasks=897752064
        Map-Reduce Framework
                Map input records=107374182
                Map output records=107374182
                Map output bytes=10952166564
                Map output materialized bytes=4697597105
                Input split bytes=52800
                Combine input records=0
                Combine output records=0
                Reduce input groups=107374182
                Reduce shuffle bytes=4697597105
                Reduce input records=107374182
                Reduce output records=107374182
                Spilled Records=214748364
                Shuffled Maps =2560
                Failed Shuffles=0
                Merged Map outputs=2560
                GC time elapsed (ms)=41384
                CPU time spent (ms)=1461460
                Physical memory (bytes) snapshot=157192347648
                Virtual memory (bytes) snapshot=514813005824
                Total committed heap usage (bytes)=186274807808
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
        File Input Format Counters
                Bytes Read=10737418200
        File Output Format Counters
                Bytes Written=10737418200
17/10/17 10:00:29 INFO terasort.TeraSort: done
9.71user 0.42system 6:54.04elapsed 2%CPU (0avgtext+0avgdata 198580maxresident)k
1008inputs+1528outputs (8major+37685minor)pagefaults 0swaps

```