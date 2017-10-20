Accidentally remove teragen first result so I regenerate it with:
```
[ernest@ip-172-32-1-58 root]$  yarn jar /opt/cloudera/parcels/CDH/jars/hadoop-examples.jar teragen -Dmapreduce.job.maps=6 -Dmapreduce.map.speculative=false -Ddfs.blocksize=32M 51200000 ouput/tgen512m

```

```
[ernest@ip-172-32-1-58 root]$ time yarn jar /opt/cloudera/parcels/CDH/jars/hadoop-examples.jar terasort ouput/tgen512m ouput/tsort512m
17/10/20 09:54:50 INFO terasort.TeraSort: starting
17/10/20 09:54:51 INFO input.FileInputFormat: Total input paths to process : 1
Spent 19ms computing base-splits.
Spent 3ms computing TeraScheduler splits.
Computing input splits took 22ms
Sampling 10 splits of 153
Making 1 from 100000 sampled records
Computing parititions took 262ms
Spent 286ms computing partitions.
17/10/20 09:54:51 INFO Configuration.deprecation: session.id is deprecated. Instead, use dfs.metrics.session-id
17/10/20 09:54:51 INFO jvm.JvmMetrics: Initializing JVM Metrics with processName=JobTracker, sessionId=
17/10/20 09:54:51 INFO mapreduce.JobSubmitter: number of splits:153
17/10/20 09:54:51 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_local809729497_0001
17/10/20 09:54:52 INFO mapred.LocalDistributedCacheManager: Creating symlink: /tmp/hadoop-ernest/mapred/local/1508493291944/_partition.lst <- /tmp/hsperfdata_ernest/_partition.lst
17/10/20 09:54:52 INFO mapred.LocalDistributedCacheManager: Localized file:/tmp/hsperfdata_ernest/ouput/tsort512m/_partition.lst as file:/tmp/hadoop-ernest/mapred/local/1508493291944/_partition.lst
17/10/20 09:54:52 INFO mapreduce.Job: The url to track the job: http://localhost:8080/
17/10/20 09:54:52 INFO mapreduce.Job: Running job: job_local809729497_0001
17/10/20 09:54:52 INFO mapred.LocalJobRunner: OutputCommitter set in config null
17/10/20 09:54:52 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/20 09:54:52 INFO mapred.LocalJobRunner: OutputCommitter is org.apache.hadoop.mapreduce.lib.output.FileOutputCommitter
17/10/20 09:54:52 INFO mapred.LocalJobRunner: Waiting for map tasks
17/10/20 09:54:52 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_000000_0
17/10/20 09:54:52 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/20 09:54:52 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:54:52 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tgen512m/part-m-00000:0+33554432
17/10/20 09:54:52 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:54:52 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:54:52 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:54:52 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:54:52 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:54:52 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/20 09:54:53 INFO mapred.LocalJobRunner:
17/10/20 09:54:53 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:54:53 INFO mapred.MapTask: Spilling map output
17/10/20 09:54:53 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/20 09:54:53 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(99488880); length = 1342177/6553600
17/10/20 09:54:53 INFO mapreduce.Job: Job job_local809729497_0001 running in uber mode : false
17/10/20 09:54:53 INFO mapreduce.Job:  map 0% reduce 0%
17/10/20 09:54:54 INFO mapred.MapTask: Finished spill 0
17/10/20 09:54:54 INFO mapred.Task: Task:attempt_local809729497_0001_m_000000_0 is done. And is in the process of committing
17/10/20 09:54:54 INFO mapred.LocalJobRunner: map
17/10/20 09:54:54 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000000_0' done.
17/10/20 09:54:54 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_000000_0
17/10/20 09:54:54 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_000001_0
17/10/20 09:54:54 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/20 09:54:54 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:54:54 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tgen512m/part-m-00000:33554432+33554432
17/10/20 09:54:54 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:54:54 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:54:54 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:54:54 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:54:54 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:54:54 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/20 09:54:54 INFO mapred.LocalJobRunner:
17/10/20 09:54:54 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:54:54 INFO mapred.MapTask: Spilling map output
17/10/20 09:54:54 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:54:54 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(99488896); length = 1342173/6553600
17/10/20 09:54:55 INFO mapreduce.Job:  map 1% reduce 0%
17/10/20 09:54:55 INFO mapred.MapTask: Finished spill 0
17/10/20 09:54:55 INFO mapred.Task: Task:attempt_local809729497_0001_m_000001_0 is done. And is in the process of committing
17/10/20 09:54:55 INFO mapred.LocalJobRunner: map
17/10/20 09:54:55 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000001_0' done.
17/10/20 09:54:55 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_000001_0
17/10/20 09:54:55 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_000002_0
17/10/20 09:54:55 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/20 09:54:55 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:54:55 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tgen512m/part-m-00000:5066719232+33554432
17/10/20 09:54:55 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:54:55 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:54:55 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:54:55 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:54:55 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:54:55 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/20 09:54:55 INFO mapred.LocalJobRunner:
17/10/20 09:54:55 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:54:55 INFO mapred.MapTask: Spilling map output
17/10/20 09:54:55 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:54:55 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(99488896); length = 1342173/6553600
17/10/20 09:54:56 INFO mapred.MapTask: Finished spill 0
17/10/20 09:54:56 INFO mapred.Task: Task:attempt_local809729497_0001_m_000002_0 is done. And is in the process of committing
17/10/20 09:54:56 INFO mapred.LocalJobRunner: map
17/10/20 09:54:56 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000002_0' done.
17/10/20 09:54:56 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_000002_0
17/10/20 09:54:56 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_000003_0
17/10/20 09:54:56 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/20 09:54:56 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:54:56 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tgen512m/part-m-00000:5033164800+33554432
17/10/20 09:54:56 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:54:56 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:54:56 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:54:56 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:54:56 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:54:56 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/20 09:54:56 INFO mapred.LocalJobRunner:
17/10/20 09:54:56 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:54:56 INFO mapred.MapTask: Spilling map output
17/10/20 09:54:56 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/20 09:54:56 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(99488880); length = 1342177/6553600
17/10/20 09:54:57 INFO mapreduce.Job:  map 2% reduce 0%
17/10/20 09:54:57 INFO mapred.MapTask: Finished spill 0
17/10/20 09:54:57 INFO mapred.Task: Task:attempt_local809729497_0001_m_000003_0 is done. And is in the process of committing
17/10/20 09:54:57 INFO mapred.LocalJobRunner: map
17/10/20 09:54:57 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000003_0' done.
17/10/20 09:54:57 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_000003_0
17/10/20 09:54:57 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_000004_0
17/10/20 09:54:57 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/20 09:54:57 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:54:57 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tgen512m/part-m-00000:4999610368+33554432
17/10/20 09:54:57 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:54:57 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:54:57 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:54:57 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:54:57 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:54:57 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/20 09:54:57 INFO mapred.LocalJobRunner:
17/10/20 09:54:57 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:54:57 INFO mapred.MapTask: Spilling map output
17/10/20 09:54:57 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:54:57 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(99488896); length = 1342173/6553600
17/10/20 09:54:58 INFO mapred.MapTask: Finished spill 0
17/10/20 09:54:58 INFO mapred.Task: Task:attempt_local809729497_0001_m_000004_0 is done. And is in the process of committing
17/10/20 09:54:58 INFO mapred.LocalJobRunner: map
17/10/20 09:54:58 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000004_0' done.
17/10/20 09:54:58 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_000004_0
17/10/20 09:54:58 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_000005_0
17/10/20 09:54:58 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/20 09:54:58 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:54:58 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tgen512m/part-m-00000:4966055936+33554432
17/10/20 09:54:58 INFO mapreduce.Job:  map 100% reduce 0%
17/10/20 09:54:58 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:54:58 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:54:58 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:54:58 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:54:58 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:54:58 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/20 09:54:58 INFO mapred.LocalJobRunner:
17/10/20 09:54:58 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:54:58 INFO mapred.MapTask: Spilling map output
17/10/20 09:54:58 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:54:58 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(99488896); length = 1342173/6553600
17/10/20 09:54:59 INFO mapred.MapTask: Finished spill 0
17/10/20 09:54:59 INFO mapred.Task: Task:attempt_local809729497_0001_m_000005_0 is done. And is in the process of committing
17/10/20 09:54:59 INFO mapred.LocalJobRunner: map
17/10/20 09:54:59 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000005_0' done.
17/10/20 09:54:59 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_000005_0
17/10/20 09:54:59 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_000006_0
17/10/20 09:54:59 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/20 09:54:59 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:54:59 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tgen512m/part-m-00000:4932501504+33554432
17/10/20 09:54:59 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:54:59 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:54:59 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:54:59 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:54:59 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:54:59 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/20 09:54:59 INFO mapred.LocalJobRunner:
17/10/20 09:54:59 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:54:59 INFO mapred.MapTask: Spilling map output
17/10/20 09:54:59 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:54:59 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(99488896); length = 1342173/6553600
17/10/20 09:55:00 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:00 INFO mapred.Task: Task:attempt_local809729497_0001_m_000006_0 is done. And is in the process of committing
17/10/20 09:55:00 INFO mapred.LocalJobRunner: map
17/10/20 09:55:00 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000006_0' done.
17/10/20 09:55:00 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_000006_0
17/10/20 09:55:00 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_000007_0
17/10/20 09:55:00 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/20 09:55:00 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:00 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tgen512m/part-m-00000:4898947072+33554432
17/10/20 09:55:00 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:00 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:00 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:00 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:00 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:00 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/20 09:55:00 INFO mapred.LocalJobRunner:
17/10/20 09:55:00 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:00 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:00 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/20 09:55:00 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(99488880); length = 1342177/6553600
17/10/20 09:55:01 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:01 INFO mapred.Task: Task:attempt_local809729497_0001_m_000007_0 is done. And is in the process of committing
17/10/20 09:55:01 INFO mapred.LocalJobRunner: map
17/10/20 09:55:01 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000007_0' done.
17/10/20 09:55:01 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_000007_0
17/10/20 09:55:01 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_000008_0
17/10/20 09:55:01 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/20 09:55:01 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:01 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tgen512m/part-m-00000:4865392640+33554432
17/10/20 09:55:01 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:01 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:01 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:01 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:01 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:01 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/20 09:55:01 INFO mapred.LocalJobRunner:
17/10/20 09:55:01 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:01 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:01 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:55:01 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(99488896); length = 1342173/6553600
17/10/20 09:55:01 INFO mapreduce.Job:  map 5% reduce 0%
17/10/20 09:55:01 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:01 INFO mapred.Task: Task:attempt_local809729497_0001_m_000008_0 is done. And is in the process of committing
17/10/20 09:55:01 INFO mapred.LocalJobRunner: map
17/10/20 09:55:01 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000008_0' done.
17/10/20 09:55:01 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_000008_0
17/10/20 09:55:01 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_000009_0
17/10/20 09:55:01 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/20 09:55:01 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:01 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tgen512m/part-m-00000:4831838208+33554432
17/10/20 09:55:02 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:02 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:02 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:02 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:02 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:02 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/20 09:55:02 INFO mapred.LocalJobRunner:
17/10/20 09:55:02 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:02 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:02 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:55:02 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(99488896); length = 1342173/6553600
17/10/20 09:55:02 INFO mapreduce.Job:  map 6% reduce 0%
17/10/20 09:55:02 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:02 INFO mapred.Task: Task:attempt_local809729497_0001_m_000009_0 is done. And is in the process of committing
17/10/20 09:55:02 INFO mapred.LocalJobRunner: map
17/10/20 09:55:02 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000009_0' done.
17/10/20 09:55:02 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_000009_0
17/10/20 09:55:02 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_000010_0
17/10/20 09:55:02 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/20 09:55:02 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:02 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tgen512m/part-m-00000:4798283776+33554432
17/10/20 09:55:02 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:02 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:02 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:02 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:02 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:02 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/20 09:55:03 INFO mapred.LocalJobRunner:
17/10/20 09:55:03 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:03 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:03 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/20 09:55:03 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(99488880); length = 1342177/6553600
17/10/20 09:55:03 INFO mapreduce.Job:  map 7% reduce 0%
17/10/20 09:55:03 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:03 INFO mapred.Task: Task:attempt_local809729497_0001_m_000010_0 is done. And is in the process of committing
17/10/20 09:55:03 INFO mapred.LocalJobRunner: map
17/10/20 09:55:03 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000010_0' done.
17/10/20 09:55:03 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_000010_0
17/10/20 09:55:03 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_000011_0
17/10/20 09:55:03 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/20 09:55:03 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:03 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tgen512m/part-m-00000:4764729344+33554432
17/10/20 09:55:03 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:03 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:03 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:03 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:03 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:03 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/20 09:55:03 INFO mapred.LocalJobRunner:
17/10/20 09:55:03 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:03 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:03 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:55:03 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(99488896); length = 1342173/6553600
17/10/20 09:55:04 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:04 INFO mapred.Task: Task:attempt_local809729497_0001_m_000011_0 is done. And is in the process of committing
17/10/20 09:55:04 INFO mapred.LocalJobRunner: map
17/10/20 09:55:04 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000011_0' done.
17/10/20 09:55:04 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_000011_0
17/10/20 09:55:04 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_000012_0
17/10/20 09:55:04 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/20 09:55:04 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:04 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tgen512m/part-m-00000:4731174912+33554432
17/10/20 09:55:04 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:04 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:04 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:04 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:04 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:04 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/20 09:55:04 INFO mapred.LocalJobRunner:
17/10/20 09:55:04 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:04 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:04 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:55:04 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(99488896); length = 1342173/6553600
17/10/20 09:55:05 INFO mapreduce.Job:  map 8% reduce 0%
17/10/20 09:55:05 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:05 INFO mapred.Task: Task:attempt_local809729497_0001_m_000012_0 is done. And is in the process of committing
17/10/20 09:55:05 INFO mapred.LocalJobRunner: map
17/10/20 09:55:05 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000012_0' done.
17/10/20 09:55:05 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_000012_0
17/10/20 09:55:05 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_000013_0
17/10/20 09:55:05 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/20 09:55:05 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:05 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tgen512m/part-m-00000:4697620480+33554432
17/10/20 09:55:05 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:05 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:05 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:05 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:05 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:05 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/20 09:55:05 INFO mapred.LocalJobRunner:
17/10/20 09:55:05 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:05 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:05 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/20 09:55:05 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(99488880); length = 1342177/6553600
17/10/20 09:55:06 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:06 INFO mapred.Task: Task:attempt_local809729497_0001_m_000013_0 is done. And is in the process of committing
17/10/20 09:55:06 INFO mapred.LocalJobRunner: map
17/10/20 09:55:06 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000013_0' done.
17/10/20 09:55:06 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_000013_0
17/10/20 09:55:06 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_000014_0
17/10/20 09:55:06 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/20 09:55:06 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:06 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tgen512m/part-m-00000:4664066048+33554432
17/10/20 09:55:06 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:06 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:06 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:06 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:06 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:06 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/20 09:55:06 INFO mapred.LocalJobRunner:
17/10/20 09:55:06 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:06 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:06 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:55:06 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(99488896); length = 1342173/6553600
17/10/20 09:55:07 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:07 INFO mapred.Task: Task:attempt_local809729497_0001_m_000014_0 is done. And is in the process of committing
17/10/20 09:55:07 INFO mapred.LocalJobRunner: map
17/10/20 09:55:07 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000014_0' done.
17/10/20 09:55:07 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_000014_0
17/10/20 09:55:07 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_000015_0
17/10/20 09:55:07 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/20 09:55:07 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:07 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tgen512m/part-m-00000:4630511616+33554432
17/10/20 09:55:07 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:07 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:07 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:07 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:07 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:07 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/20 09:55:07 INFO mapreduce.Job:  map 100% reduce 0%
17/10/20 09:55:07 INFO mapred.LocalJobRunner:
17/10/20 09:55:07 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:07 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:07 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:55:07 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(99488896); length = 1342173/6553600
17/10/20 09:55:08 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:08 INFO mapred.Task: Task:attempt_local809729497_0001_m_000015_0 is done. And is in the process of committing
17/10/20 09:55:08 INFO mapred.LocalJobRunner: map
17/10/20 09:55:08 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000015_0' done.
17/10/20 09:55:08 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_000015_0
17/10/20 09:55:08 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_000016_0
17/10/20 09:55:08 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/20 09:55:08 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:08 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tgen512m/part-m-00000:4596957184+33554432
17/10/20 09:55:08 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:08 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:08 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:08 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:08 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:08 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/20 09:55:08 INFO mapred.LocalJobRunner:
17/10/20 09:55:08 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:08 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:08 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/20 09:55:08 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(99488880); length = 1342177/6553600
17/10/20 09:55:08 INFO mapreduce.Job:  map 10% reduce 0%
17/10/20 09:55:09 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:09 INFO mapred.Task: Task:attempt_local809729497_0001_m_000016_0 is done. And is in the process of committing
17/10/20 09:55:09 INFO mapred.LocalJobRunner: map
17/10/20 09:55:09 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000016_0' done.
17/10/20 09:55:09 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_000016_0
17/10/20 09:55:09 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_000017_0
17/10/20 09:55:09 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/20 09:55:09 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:09 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tgen512m/part-m-00000:4563402752+33554432
17/10/20 09:55:09 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:09 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:09 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:09 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:09 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:09 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/20 09:55:09 INFO mapred.LocalJobRunner:
17/10/20 09:55:09 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:09 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:09 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:55:09 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(99488896); length = 1342173/6553600
17/10/20 09:55:09 INFO mapreduce.Job:  map 11% reduce 0%
17/10/20 09:55:09 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:09 INFO mapred.Task: Task:attempt_local809729497_0001_m_000017_0 is done. And is in the process of committing
17/10/20 09:55:09 INFO mapred.LocalJobRunner: map
17/10/20 09:55:09 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000017_0' done.
17/10/20 09:55:09 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_000017_0
17/10/20 09:55:09 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_000018_0
17/10/20 09:55:09 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/20 09:55:09 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:09 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tgen512m/part-m-00000:4529848320+33554432
17/10/20 09:55:09 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:09 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:09 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:09 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:09 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:09 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/20 09:55:09 INFO mapred.LocalJobRunner:
17/10/20 09:55:09 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:09 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:09 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:55:09 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(99488896); length = 1342173/6553600
17/10/20 09:55:10 INFO mapreduce.Job:  map 12% reduce 0%
17/10/20 09:55:10 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:10 INFO mapred.Task: Task:attempt_local809729497_0001_m_000018_0 is done. And is in the process of committing
17/10/20 09:55:10 INFO mapred.LocalJobRunner: map
17/10/20 09:55:10 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000018_0' done.
17/10/20 09:55:10 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_000018_0
17/10/20 09:55:10 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_000019_0
17/10/20 09:55:10 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/20 09:55:10 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:10 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tgen512m/part-m-00000:4496293888+33554432
17/10/20 09:55:10 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:10 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:10 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:10 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:10 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:10 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/20 09:55:10 INFO mapred.LocalJobRunner:
17/10/20 09:55:10 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:10 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:10 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/20 09:55:10 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(99488880); length = 1342177/6553600
17/10/20 09:55:11 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:11 INFO mapred.Task: Task:attempt_local809729497_0001_m_000019_0 is done. And is in the process of committing
17/10/20 09:55:11 INFO mapred.LocalJobRunner: map
17/10/20 09:55:11 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000019_0' done.
17/10/20 09:55:11 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_000019_0
17/10/20 09:55:11 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_000020_0
17/10/20 09:55:11 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/20 09:55:11 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:11 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tgen512m/part-m-00000:4462739456+33554432
17/10/20 09:55:11 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:11 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:11 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:11 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:11 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:11 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/20 09:55:11 INFO mapred.LocalJobRunner:
17/10/20 09:55:11 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:11 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:11 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:55:11 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(99488896); length = 1342173/6553600
17/10/20 09:55:12 INFO mapreduce.Job:  map 13% reduce 0%
17/10/20 09:55:12 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:12 INFO mapred.Task: Task:attempt_local809729497_0001_m_000020_0 is done. And is in the process of committing
17/10/20 09:55:12 INFO mapred.LocalJobRunner: map
17/10/20 09:55:12 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000020_0' done.
17/10/20 09:55:12 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_000020_0
17/10/20 09:55:12 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_000021_0
17/10/20 09:55:12 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/20 09:55:12 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:12 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tgen512m/part-m-00000:4429185024+33554432
17/10/20 09:55:12 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:12 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:12 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:12 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:12 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:12 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/20 09:55:12 INFO mapred.LocalJobRunner:
17/10/20 09:55:12 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:12 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:12 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:55:12 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(99488896); length = 1342173/6553600
17/10/20 09:55:13 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:13 INFO mapred.Task: Task:attempt_local809729497_0001_m_000021_0 is done. And is in the process of committing
17/10/20 09:55:13 INFO mapred.LocalJobRunner: map
17/10/20 09:55:13 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000021_0' done.
17/10/20 09:55:13 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_000021_0
17/10/20 09:55:13 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_000022_0
17/10/20 09:55:13 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/20 09:55:13 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:13 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tgen512m/part-m-00000:4395630592+33554432
17/10/20 09:55:13 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:13 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:13 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:13 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:13 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:13 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/20 09:55:13 INFO mapreduce.Job:  map 100% reduce 0%
17/10/20 09:55:13 INFO mapred.LocalJobRunner:
17/10/20 09:55:13 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:13 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:13 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/20 09:55:13 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(99488880); length = 1342177/6553600
17/10/20 09:55:14 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:14 INFO mapred.Task: Task:attempt_local809729497_0001_m_000022_0 is done. And is in the process of committing
17/10/20 09:55:14 INFO mapred.LocalJobRunner: map
17/10/20 09:55:14 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000022_0' done.
17/10/20 09:55:14 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_000022_0
17/10/20 09:55:14 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_000023_0
17/10/20 09:55:14 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/20 09:55:14 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:14 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tgen512m/part-m-00000:4362076160+33554432
17/10/20 09:55:14 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:14 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:14 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:14 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:14 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:14 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/20 09:55:14 INFO mapred.LocalJobRunner:
17/10/20 09:55:14 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:14 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:14 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:55:14 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(99488896); length = 1342173/6553600
17/10/20 09:55:14 INFO mapreduce.Job:  map 15% reduce 0%
17/10/20 09:55:14 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:14 INFO mapred.Task: Task:attempt_local809729497_0001_m_000023_0 is done. And is in the process of committing
17/10/20 09:55:14 INFO mapred.LocalJobRunner: map
17/10/20 09:55:14 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000023_0' done.
17/10/20 09:55:14 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_000023_0
17/10/20 09:55:14 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_000024_0
17/10/20 09:55:14 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/20 09:55:14 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:14 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tgen512m/part-m-00000:4328521728+33554432
17/10/20 09:55:14 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:14 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:14 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:14 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:14 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:14 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/20 09:55:15 INFO mapred.LocalJobRunner:
17/10/20 09:55:15 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:15 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:15 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:55:15 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(99488896); length = 1342173/6553600
17/10/20 09:55:15 INFO mapreduce.Job:  map 16% reduce 0%
17/10/20 09:55:15 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:15 INFO mapred.Task: Task:attempt_local809729497_0001_m_000024_0 is done. And is in the process of committing
17/10/20 09:55:15 INFO mapred.LocalJobRunner: map
17/10/20 09:55:15 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000024_0' done.
17/10/20 09:55:15 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_000024_0
17/10/20 09:55:15 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_000025_0
17/10/20 09:55:15 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/20 09:55:15 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:15 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tgen512m/part-m-00000:4294967296+33554432
17/10/20 09:55:15 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:15 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:15 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:15 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:15 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:15 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/20 09:55:16 INFO mapred.LocalJobRunner:
17/10/20 09:55:16 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:16 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:16 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/20 09:55:16 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(99488880); length = 1342177/6553600
17/10/20 09:55:16 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:16 INFO mapred.Task: Task:attempt_local809729497_0001_m_000025_0 is done. And is in the process of committing
17/10/20 09:55:16 INFO mapred.LocalJobRunner: map
17/10/20 09:55:16 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000025_0' done.
17/10/20 09:55:16 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_000025_0
17/10/20 09:55:16 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_000026_0
17/10/20 09:55:16 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/20 09:55:16 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:16 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tgen512m/part-m-00000:4261412864+33554432
17/10/20 09:55:16 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:16 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:16 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:16 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:16 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:16 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/20 09:55:16 INFO mapred.LocalJobRunner:
17/10/20 09:55:16 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:16 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:16 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:55:16 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(99488896); length = 1342173/6553600
17/10/20 09:55:17 INFO mapreduce.Job:  map 17% reduce 0%
17/10/20 09:55:17 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:17 INFO mapred.Task: Task:attempt_local809729497_0001_m_000026_0 is done. And is in the process of committing
17/10/20 09:55:17 INFO mapred.LocalJobRunner: map
17/10/20 09:55:17 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000026_0' done.
17/10/20 09:55:17 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_000026_0
17/10/20 09:55:17 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_000027_0
17/10/20 09:55:17 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/20 09:55:17 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:17 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tgen512m/part-m-00000:4227858432+33554432
17/10/20 09:55:17 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:17 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:17 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:17 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:17 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:17 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/20 09:55:17 INFO mapred.LocalJobRunner:
17/10/20 09:55:17 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:17 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:17 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:55:17 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(99488896); length = 1342173/6553600
17/10/20 09:55:18 INFO mapreduce.Job:  map 18% reduce 0%
17/10/20 09:55:18 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:18 INFO mapred.Task: Task:attempt_local809729497_0001_m_000027_0 is done. And is in the process of committing
17/10/20 09:55:18 INFO mapred.LocalJobRunner: map
17/10/20 09:55:18 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000027_0' done.
17/10/20 09:55:18 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_000027_0
17/10/20 09:55:18 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_000028_0
17/10/20 09:55:18 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/20 09:55:18 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:18 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tgen512m/part-m-00000:4194304000+33554432
17/10/20 09:55:18 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:18 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:18 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:18 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:18 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:18 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/20 09:55:18 INFO mapred.LocalJobRunner:
17/10/20 09:55:18 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:18 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:18 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/20 09:55:18 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(99488880); length = 1342177/6553600
17/10/20 09:55:19 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:19 INFO mapred.Task: Task:attempt_local809729497_0001_m_000028_0 is done. And is in the process of committing
17/10/20 09:55:19 INFO mapred.LocalJobRunner: map
17/10/20 09:55:19 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000028_0' done.
17/10/20 09:55:19 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_000028_0
17/10/20 09:55:19 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_000029_0
17/10/20 09:55:19 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/20 09:55:19 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:19 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tgen512m/part-m-00000:4160749568+33554432
17/10/20 09:55:19 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:19 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:19 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:19 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:19 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:19 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/20 09:55:19 INFO mapred.LocalJobRunner:
17/10/20 09:55:19 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:19 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:19 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:55:19 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(99488896); length = 1342173/6553600
17/10/20 09:55:19 INFO mapreduce.Job:  map 19% reduce 0%
17/10/20 09:55:20 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:20 INFO mapred.Task: Task:attempt_local809729497_0001_m_000029_0 is done. And is in the process of committing
17/10/20 09:55:20 INFO mapred.LocalJobRunner: map
17/10/20 09:55:20 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000029_0' done.
17/10/20 09:55:20 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_000029_0
17/10/20 09:55:20 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_000030_0
17/10/20 09:55:20 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/20 09:55:20 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:20 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tgen512m/part-m-00000:4127195136+33554432
17/10/20 09:55:20 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:20 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:20 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:20 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:20 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:20 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/20 09:55:20 INFO mapred.LocalJobRunner:
17/10/20 09:55:20 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:20 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:20 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:55:20 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(99488896); length = 1342173/6553600
17/10/20 09:55:20 INFO mapreduce.Job:  map 20% reduce 0%
17/10/20 09:55:20 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:20 INFO mapred.Task: Task:attempt_local809729497_0001_m_000030_0 is done. And is in the process of committing
17/10/20 09:55:20 INFO mapred.LocalJobRunner: map
17/10/20 09:55:20 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000030_0' done.
17/10/20 09:55:20 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_000030_0
17/10/20 09:55:20 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_000031_0
17/10/20 09:55:20 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/20 09:55:20 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:20 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tgen512m/part-m-00000:4093640704+33554432
17/10/20 09:55:20 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:20 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:20 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:20 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:20 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:20 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/20 09:55:21 INFO mapred.LocalJobRunner:
17/10/20 09:55:21 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:21 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:21 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:55:21 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(99488896); length = 1342173/6553600
17/10/20 09:55:21 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:21 INFO mapred.Task: Task:attempt_local809729497_0001_m_000031_0 is done. And is in the process of committing
17/10/20 09:55:21 INFO mapred.LocalJobRunner: map
17/10/20 09:55:21 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000031_0' done.
17/10/20 09:55:21 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_000031_0
17/10/20 09:55:21 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_000032_0
17/10/20 09:55:21 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/20 09:55:21 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:21 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tgen512m/part-m-00000:4060086272+33554432
17/10/20 09:55:21 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:21 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:21 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:21 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:21 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:21 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/20 09:55:21 INFO mapred.LocalJobRunner:
17/10/20 09:55:21 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:21 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:21 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/20 09:55:21 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(99488880); length = 1342177/6553600
17/10/20 09:55:22 INFO mapreduce.Job:  map 21% reduce 0%
17/10/20 09:55:22 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:22 INFO mapred.Task: Task:attempt_local809729497_0001_m_000032_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:55:22 INFO mapred.LocalJobRunner: map
17/10/20 09:55:22 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000032_0' done.
17/10/20 09:55:22 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00032_0
17/10/20 09:55:22 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0033_0
17/10/20 09:55:22 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:55:22 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:22 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:4026531840+33554432
17/10/20 09:55:22 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:22 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:22 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:22 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:22 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:22 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:55:22 INFO mapred.LocalJobRunner:
17/10/20 09:55:22 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:22 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:22 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:55:22 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:55:23 INFO mapreduce.Job:  map 22% reduce 0%
17/10/20 09:55:23 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:23 INFO mapred.Task: Task:attempt_local809729497_0001_m_000033_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:55:23 INFO mapred.LocalJobRunner: map
17/10/20 09:55:23 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000033_0' done.
17/10/20 09:55:23 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00033_0
17/10/20 09:55:23 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0034_0
17/10/20 09:55:23 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:55:23 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:23 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:3992977408+33554432
17/10/20 09:55:23 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:23 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:23 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:23 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:23 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:23 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:55:23 INFO mapred.LocalJobRunner:
17/10/20 09:55:23 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:23 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:23 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:55:23 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:55:24 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:24 INFO mapred.Task: Task:attempt_local809729497_0001_m_000034_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:55:24 INFO mapred.LocalJobRunner: map
17/10/20 09:55:24 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000034_0' done.
17/10/20 09:55:24 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00034_0
17/10/20 09:55:24 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0035_0
17/10/20 09:55:24 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:55:24 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:24 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:3959422976+33554432
17/10/20 09:55:24 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:24 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:24 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:24 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:24 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:24 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:55:24 INFO mapreduce.Job:  map 100% reduce 0%
17/10/20 09:55:24 INFO mapred.LocalJobRunner:
17/10/20 09:55:24 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:24 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:24 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/20 09:55:24 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(994888                                                                                                                         80); length = 1342177/6553600
17/10/20 09:55:25 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:25 INFO mapred.Task: Task:attempt_local809729497_0001_m_000035_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:55:25 INFO mapred.LocalJobRunner: map
17/10/20 09:55:25 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000035_0' done.
17/10/20 09:55:25 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00035_0
17/10/20 09:55:25 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0036_0
17/10/20 09:55:25 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:55:25 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:25 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:3925868544+33554432
17/10/20 09:55:25 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:25 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:25 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:25 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:25 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:25 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:55:25 INFO mapred.LocalJobRunner:
17/10/20 09:55:25 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:25 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:25 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:55:25 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:55:25 INFO mapreduce.Job:  map 24% reduce 0%
17/10/20 09:55:26 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:26 INFO mapred.Task: Task:attempt_local809729497_0001_m_000036_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:55:26 INFO mapred.LocalJobRunner: map
17/10/20 09:55:26 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000036_0' done.
17/10/20 09:55:26 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00036_0
17/10/20 09:55:26 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0037_0
17/10/20 09:55:26 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:55:26 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:26 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:3892314112+33554432
17/10/20 09:55:26 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:26 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:26 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:26 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:26 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:26 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:55:26 INFO mapred.LocalJobRunner:
17/10/20 09:55:26 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:26 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:26 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:55:26 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:55:26 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:26 INFO mapred.Task: Task:attempt_local809729497_0001_m_000037_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:55:26 INFO mapred.LocalJobRunner: map
17/10/20 09:55:26 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000037_0' done.
17/10/20 09:55:26 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00037_0
17/10/20 09:55:26 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0038_0
17/10/20 09:55:26 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:55:26 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:26 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:3858759680+33554432
17/10/20 09:55:26 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:26 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:26 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:26 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:26 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:26 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:55:27 INFO mapred.LocalJobRunner:
17/10/20 09:55:27 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:27 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:27 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/20 09:55:27 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(994888                                                                                                                         80); length = 1342177/6553600
17/10/20 09:55:27 INFO mapreduce.Job:  map 25% reduce 0%
17/10/20 09:55:27 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:27 INFO mapred.Task: Task:attempt_local809729497_0001_m_000038_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:55:27 INFO mapred.LocalJobRunner: map
17/10/20 09:55:27 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000038_0' done.
17/10/20 09:55:27 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00038_0
17/10/20 09:55:27 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0039_0
17/10/20 09:55:27 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:55:27 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:27 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:3825205248+33554432
17/10/20 09:55:27 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:27 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:27 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:27 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:27 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:27 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:55:27 INFO mapred.LocalJobRunner:
17/10/20 09:55:27 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:27 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:27 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:55:27 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:55:28 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:28 INFO mapred.Task: Task:attempt_local809729497_0001_m_000039_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:55:28 INFO mapred.LocalJobRunner: map
17/10/20 09:55:28 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000039_0' done.
17/10/20 09:55:28 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00039_0
17/10/20 09:55:28 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0040_0
17/10/20 09:55:28 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:55:28 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:28 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:3791650816+33554432
17/10/20 09:55:28 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:28 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:28 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:28 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:28 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:28 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:55:28 INFO mapred.LocalJobRunner:
17/10/20 09:55:28 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:28 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:28 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:55:28 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:55:29 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:29 INFO mapred.Task: Task:attempt_local809729497_0001_m_000040_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:55:29 INFO mapred.LocalJobRunner: map
17/10/20 09:55:29 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000040_0' done.
17/10/20 09:55:29 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00040_0
17/10/20 09:55:29 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0041_0
17/10/20 09:55:29 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:55:29 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:29 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:3758096384+33554432
17/10/20 09:55:29 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:29 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:29 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:29 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:29 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:29 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:55:29 INFO mapreduce.Job:  map 100% reduce 0%
17/10/20 09:55:29 INFO mapred.LocalJobRunner:
17/10/20 09:55:29 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:29 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:29 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/20 09:55:29 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(994888                                                                                                                         80); length = 1342177/6553600
17/10/20 09:55:30 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:30 INFO mapred.Task: Task:attempt_local809729497_0001_m_000041_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:55:30 INFO mapred.LocalJobRunner: map
17/10/20 09:55:30 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000041_0' done.
17/10/20 09:55:30 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00041_0
17/10/20 09:55:30 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0042_0
17/10/20 09:55:30 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:55:30 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:30 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:3724541952+33554432
17/10/20 09:55:30 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:30 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:30 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:30 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:30 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:30 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:55:30 INFO mapred.LocalJobRunner:
17/10/20 09:55:30 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:30 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:30 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:55:30 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:55:31 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:31 INFO mapred.Task: Task:attempt_local809729497_0001_m_000042_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:55:31 INFO mapred.LocalJobRunner: map
17/10/20 09:55:31 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000042_0' done.
17/10/20 09:55:31 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00042_0
17/10/20 09:55:31 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0043_0
17/10/20 09:55:31 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:55:31 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:31 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:3690987520+33554432
17/10/20 09:55:31 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:31 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:31 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:31 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:31 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:31 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:55:31 INFO mapred.LocalJobRunner:
17/10/20 09:55:31 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:31 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:31 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:55:31 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:55:32 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:32 INFO mapred.Task: Task:attempt_local809729497_0001_m_000043_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:55:32 INFO mapred.LocalJobRunner: map
17/10/20 09:55:32 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000043_0' done.
17/10/20 09:55:32 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00043_0
17/10/20 09:55:32 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0044_0
17/10/20 09:55:32 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:55:32 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:32 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:3657433088+33554432
17/10/20 09:55:32 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:32 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:32 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:32 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:32 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:32 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:55:32 INFO mapred.LocalJobRunner:
17/10/20 09:55:32 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:32 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:32 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/20 09:55:32 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(994888                                                                                                                         80); length = 1342177/6553600
17/10/20 09:55:32 INFO mapreduce.Job:  map 29% reduce 0%
17/10/20 09:55:33 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:33 INFO mapred.Task: Task:attempt_local809729497_0001_m_000044_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:55:33 INFO mapred.LocalJobRunner: map
17/10/20 09:55:33 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000044_0' done.
17/10/20 09:55:33 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00044_0
17/10/20 09:55:33 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0045_0
17/10/20 09:55:33 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:55:33 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:33 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:3623878656+33554432
17/10/20 09:55:33 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:33 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:33 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:33 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:33 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:33 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:55:33 INFO mapred.LocalJobRunner:
17/10/20 09:55:33 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:33 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:33 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:55:33 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:55:34 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:34 INFO mapred.Task: Task:attempt_local809729497_0001_m_000045_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:55:34 INFO mapred.LocalJobRunner: map
17/10/20 09:55:34 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000045_0' done.
17/10/20 09:55:34 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00045_0
17/10/20 09:55:34 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0046_0
17/10/20 09:55:34 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:55:34 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:34 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:3590324224+33554432
17/10/20 09:55:34 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:34 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:34 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:34 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:34 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:34 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:55:34 INFO mapred.LocalJobRunner:
17/10/20 09:55:34 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:34 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:34 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:55:34 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:55:34 INFO mapreduce.Job:  map 30% reduce 0%
17/10/20 09:55:34 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:34 INFO mapred.Task: Task:attempt_local809729497_0001_m_000046_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:55:34 INFO mapred.LocalJobRunner: map
17/10/20 09:55:34 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000046_0' done.
17/10/20 09:55:34 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00046_0
17/10/20 09:55:34 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0047_0
17/10/20 09:55:34 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:55:34 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:34 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:3556769792+33554432
17/10/20 09:55:34 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:34 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:34 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:34 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:34 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:34 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:55:35 INFO mapred.LocalJobRunner:
17/10/20 09:55:35 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:35 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:35 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/20 09:55:35 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(994888                                                                                                                         80); length = 1342177/6553600
17/10/20 09:55:35 INFO mapreduce.Job:  map 31% reduce 0%
17/10/20 09:55:35 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:35 INFO mapred.Task: Task:attempt_local809729497_0001_m_000047_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:55:35 INFO mapred.LocalJobRunner: map
17/10/20 09:55:35 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000047_0' done.
17/10/20 09:55:35 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00047_0
17/10/20 09:55:35 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0048_0
17/10/20 09:55:35 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:55:35 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:35 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:3523215360+33554432
17/10/20 09:55:35 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:35 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:35 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:35 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:35 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:35 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:55:36 INFO mapred.LocalJobRunner:
17/10/20 09:55:36 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:36 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:36 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:55:36 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:55:36 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:36 INFO mapred.Task: Task:attempt_local809729497_0001_m_000048_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:55:36 INFO mapred.LocalJobRunner: map
17/10/20 09:55:36 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000048_0' done.
17/10/20 09:55:36 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00048_0
17/10/20 09:55:36 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0049_0
17/10/20 09:55:36 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:55:36 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:36 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:3489660928+33554432
17/10/20 09:55:36 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:36 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:36 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:36 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:36 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:36 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:55:36 INFO mapred.LocalJobRunner:
17/10/20 09:55:36 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:36 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:36 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:55:36 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:55:37 INFO mapreduce.Job:  map 32% reduce 0%
17/10/20 09:55:37 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:37 INFO mapred.Task: Task:attempt_local809729497_0001_m_000049_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:55:37 INFO mapred.LocalJobRunner: map
17/10/20 09:55:37 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000049_0' done.
17/10/20 09:55:37 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00049_0
17/10/20 09:55:37 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0050_0
17/10/20 09:55:37 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:55:37 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:37 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:3456106496+33554432
17/10/20 09:55:37 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:37 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:37 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:37 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:37 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:37 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:55:37 INFO mapred.LocalJobRunner:
17/10/20 09:55:37 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:37 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:37 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/20 09:55:37 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(994888                                                                                                                         80); length = 1342177/6553600
17/10/20 09:55:38 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:38 INFO mapred.Task: Task:attempt_local809729497_0001_m_000050_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:55:38 INFO mapred.LocalJobRunner: map
17/10/20 09:55:38 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000050_0' done.
17/10/20 09:55:38 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00050_0
17/10/20 09:55:38 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0051_0
17/10/20 09:55:38 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:55:38 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:38 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:3422552064+33554432
17/10/20 09:55:38 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:38 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:38 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:38 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:38 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:38 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:55:38 INFO mapreduce.Job:  map 100% reduce 0%
17/10/20 09:55:38 INFO mapred.LocalJobRunner:
17/10/20 09:55:38 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:38 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:38 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:55:38 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:55:39 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:39 INFO mapred.Task: Task:attempt_local809729497_0001_m_000051_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:55:39 INFO mapred.LocalJobRunner: map
17/10/20 09:55:39 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000051_0' done.
17/10/20 09:55:39 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00051_0
17/10/20 09:55:39 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0052_0
17/10/20 09:55:39 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:55:39 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:39 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:3388997632+33554432
17/10/20 09:55:39 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:39 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:39 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:39 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:39 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:39 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:55:39 INFO mapred.LocalJobRunner:
17/10/20 09:55:39 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:39 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:39 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:55:39 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:55:40 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:40 INFO mapred.Task: Task:attempt_local809729497_0001_m_000052_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:55:40 INFO mapred.LocalJobRunner: map
17/10/20 09:55:40 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000052_0' done.
17/10/20 09:55:40 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00052_0
17/10/20 09:55:40 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0053_0
17/10/20 09:55:40 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:55:40 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:40 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:3355443200+33554432
17/10/20 09:55:40 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:40 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:40 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:40 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:40 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:40 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:55:40 INFO mapred.LocalJobRunner:
17/10/20 09:55:40 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:40 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:40 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/20 09:55:40 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(994888                                                                                                                         80); length = 1342177/6553600
17/10/20 09:55:40 INFO mapreduce.Job:  map 35% reduce 0%
17/10/20 09:55:41 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:41 INFO mapred.Task: Task:attempt_local809729497_0001_m_000053_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:55:41 INFO mapred.LocalJobRunner: map
17/10/20 09:55:41 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000053_0' done.
17/10/20 09:55:41 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00053_0
17/10/20 09:55:41 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0054_0
17/10/20 09:55:41 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:55:41 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:41 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:3321888768+33554432
17/10/20 09:55:41 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:41 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:41 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:41 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:41 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:41 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:55:41 INFO mapred.LocalJobRunner:
17/10/20 09:55:41 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:41 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:41 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:55:41 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:55:41 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:41 INFO mapred.Task: Task:attempt_local809729497_0001_m_000054_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:55:41 INFO mapred.LocalJobRunner: map
17/10/20 09:55:41 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000054_0' done.
17/10/20 09:55:41 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00054_0
17/10/20 09:55:41 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0055_0
17/10/20 09:55:41 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:55:41 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:41 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:3288334336+33554432
17/10/20 09:55:41 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:41 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:41 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:41 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:41 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:41 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:55:42 INFO mapred.LocalJobRunner:
17/10/20 09:55:42 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:42 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:42 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:55:42 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:55:42 INFO mapreduce.Job:  map 36% reduce 0%
17/10/20 09:55:42 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:42 INFO mapred.Task: Task:attempt_local809729497_0001_m_000055_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:55:42 INFO mapred.LocalJobRunner: map
17/10/20 09:55:42 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000055_0' done.
17/10/20 09:55:42 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00055_0
17/10/20 09:55:42 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0056_0
17/10/20 09:55:42 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:55:42 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:42 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:3254779904+33554432
17/10/20 09:55:42 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:42 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:42 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:42 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:42 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:42 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:55:42 INFO mapred.LocalJobRunner:
17/10/20 09:55:42 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:42 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:42 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:55:42 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:55:43 INFO mapreduce.Job:  map 37% reduce 0%
17/10/20 09:55:43 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:43 INFO mapred.Task: Task:attempt_local809729497_0001_m_000056_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:55:43 INFO mapred.LocalJobRunner: map
17/10/20 09:55:43 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000056_0' done.
17/10/20 09:55:43 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00056_0
17/10/20 09:55:43 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0057_0
17/10/20 09:55:43 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:55:43 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:43 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:3221225472+33554432
17/10/20 09:55:43 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:43 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:43 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:43 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:43 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:43 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:55:43 INFO mapred.LocalJobRunner:
17/10/20 09:55:43 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:43 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:43 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/20 09:55:43 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(994888                                                                                                                         80); length = 1342177/6553600
17/10/20 09:55:44 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:44 INFO mapred.Task: Task:attempt_local809729497_0001_m_000057_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:55:44 INFO mapred.LocalJobRunner: map
17/10/20 09:55:44 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000057_0' done.
17/10/20 09:55:44 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00057_0
17/10/20 09:55:44 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0058_0
17/10/20 09:55:44 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:55:44 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:44 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:3187671040+33554432
17/10/20 09:55:44 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:44 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:44 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:44 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:44 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:44 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:55:44 INFO mapreduce.Job:  map 100% reduce 0%
17/10/20 09:55:44 INFO mapred.LocalJobRunner:
17/10/20 09:55:44 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:44 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:44 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:55:44 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:55:45 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:45 INFO mapred.Task: Task:attempt_local809729497_0001_m_000058_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:55:45 INFO mapred.LocalJobRunner: map
17/10/20 09:55:45 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000058_0' done.
17/10/20 09:55:45 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00058_0
17/10/20 09:55:45 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0059_0
17/10/20 09:55:45 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:55:45 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:45 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:3154116608+33554432
17/10/20 09:55:45 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:45 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:45 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:45 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:45 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:45 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:55:45 INFO mapred.LocalJobRunner:
17/10/20 09:55:45 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:45 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:45 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:55:45 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:55:46 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:46 INFO mapred.Task: Task:attempt_local809729497_0001_m_000059_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:55:46 INFO mapred.LocalJobRunner: map
17/10/20 09:55:46 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000059_0' done.
17/10/20 09:55:46 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00059_0
17/10/20 09:55:46 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0060_0
17/10/20 09:55:46 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:55:46 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:46 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:3120562176+33554432
17/10/20 09:55:46 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:46 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:46 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:46 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:46 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:46 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:55:46 INFO mapred.LocalJobRunner:
17/10/20 09:55:46 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:46 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:46 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/20 09:55:46 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(994888                                                                                                                         80); length = 1342177/6553600
17/10/20 09:55:46 INFO mapreduce.Job:  map 39% reduce 0%
17/10/20 09:55:46 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:46 INFO mapred.Task: Task:attempt_local809729497_0001_m_000060_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:55:46 INFO mapred.LocalJobRunner: map
17/10/20 09:55:46 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000060_0' done.
17/10/20 09:55:46 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00060_0
17/10/20 09:55:46 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0061_0
17/10/20 09:55:46 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:55:46 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:46 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:3087007744+33554432
17/10/20 09:55:46 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:46 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:46 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:46 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:46 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:46 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:55:47 INFO mapred.LocalJobRunner:
17/10/20 09:55:47 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:47 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:47 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:55:47 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:55:47 INFO mapreduce.Job:  map 40% reduce 0%
17/10/20 09:55:47 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:47 INFO mapred.Task: Task:attempt_local809729497_0001_m_000061_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:55:47 INFO mapred.LocalJobRunner: map
17/10/20 09:55:47 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000061_0' done.
17/10/20 09:55:47 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00061_0
17/10/20 09:55:47 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0062_0
17/10/20 09:55:47 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:55:47 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:47 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:3053453312+33554432
17/10/20 09:55:47 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:47 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:47 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:47 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:47 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:47 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:55:47 INFO mapred.LocalJobRunner:
17/10/20 09:55:47 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:47 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:47 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:55:47 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:55:48 INFO mapreduce.Job:  map 41% reduce 0%
17/10/20 09:55:48 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:48 INFO mapred.Task: Task:attempt_local809729497_0001_m_000062_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:55:48 INFO mapred.LocalJobRunner: map
17/10/20 09:55:48 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000062_0' done.
17/10/20 09:55:48 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00062_0
17/10/20 09:55:48 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0063_0
17/10/20 09:55:48 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:55:48 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:48 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:3019898880+33554432
17/10/20 09:55:48 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:48 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:48 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:48 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:48 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:48 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:55:48 INFO mapred.LocalJobRunner:
17/10/20 09:55:48 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:48 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:48 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/20 09:55:48 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(994888                                                                                                                         80); length = 1342177/6553600
17/10/20 09:55:49 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:49 INFO mapred.Task: Task:attempt_local809729497_0001_m_000063_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:55:49 INFO mapred.LocalJobRunner: map
17/10/20 09:55:49 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000063_0' done.
17/10/20 09:55:49 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00063_0
17/10/20 09:55:49 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0064_0
17/10/20 09:55:49 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:55:49 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:49 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:2986344448+33554432
17/10/20 09:55:49 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:49 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:49 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:49 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:49 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:49 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:55:49 INFO mapred.LocalJobRunner:
17/10/20 09:55:49 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:49 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:49 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:55:49 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:55:50 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:50 INFO mapred.Task: Task:attempt_local809729497_0001_m_000064_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:55:50 INFO mapred.LocalJobRunner: map
17/10/20 09:55:50 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000064_0' done.
17/10/20 09:55:50 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00064_0
17/10/20 09:55:50 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0065_0
17/10/20 09:55:50 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:55:50 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:50 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:2952790016+33554432
17/10/20 09:55:50 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:50 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:50 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:50 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:50 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:50 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:55:50 INFO mapreduce.Job:  map 100% reduce 0%
17/10/20 09:55:50 INFO mapred.LocalJobRunner:
17/10/20 09:55:50 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:50 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:50 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:55:50 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:55:51 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:51 INFO mapred.Task: Task:attempt_local809729497_0001_m_000065_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:55:51 INFO mapred.LocalJobRunner: map
17/10/20 09:55:51 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000065_0' done.
17/10/20 09:55:51 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00065_0
17/10/20 09:55:51 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0066_0
17/10/20 09:55:51 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:55:51 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:51 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:2919235584+33554432
17/10/20 09:55:51 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:51 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:51 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:51 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:51 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:51 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:55:51 INFO mapred.LocalJobRunner:
17/10/20 09:55:51 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:51 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:51 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/20 09:55:51 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(994888                                                                                                                         80); length = 1342177/6553600
17/10/20 09:55:51 INFO mapreduce.Job:  map 43% reduce 0%
17/10/20 09:55:51 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:51 INFO mapred.Task: Task:attempt_local809729497_0001_m_000066_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:55:51 INFO mapred.LocalJobRunner: map
17/10/20 09:55:51 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000066_0' done.
17/10/20 09:55:51 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00066_0
17/10/20 09:55:51 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0067_0
17/10/20 09:55:51 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:55:51 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:51 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:2885681152+33554432
17/10/20 09:55:51 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:51 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:51 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:51 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:51 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:51 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:55:52 INFO mapred.LocalJobRunner:
17/10/20 09:55:52 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:52 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:52 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:55:52 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:55:52 INFO mapreduce.Job:  map 44% reduce 0%
17/10/20 09:55:52 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:52 INFO mapred.Task: Task:attempt_local809729497_0001_m_000067_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:55:52 INFO mapred.LocalJobRunner: map
17/10/20 09:55:52 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000067_0' done.
17/10/20 09:55:52 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00067_0
17/10/20 09:55:52 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0068_0
17/10/20 09:55:52 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:55:52 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:52 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:2852126720+33554432
17/10/20 09:55:52 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:52 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:52 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:52 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:52 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:52 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:55:53 INFO mapred.LocalJobRunner:
17/10/20 09:55:53 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:53 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:53 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:55:53 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:55:53 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:53 INFO mapred.Task: Task:attempt_local809729497_0001_m_000068_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:55:53 INFO mapred.LocalJobRunner: map
17/10/20 09:55:53 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000068_0' done.
17/10/20 09:55:53 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00068_0
17/10/20 09:55:53 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0069_0
17/10/20 09:55:53 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:55:53 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:53 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:2818572288+33554432
17/10/20 09:55:53 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:53 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:53 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:53 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:53 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:53 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:55:53 INFO mapred.LocalJobRunner:
17/10/20 09:55:53 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:53 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:53 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/20 09:55:53 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(994888                                                                                                                         80); length = 1342177/6553600
17/10/20 09:55:54 INFO mapreduce.Job:  map 45% reduce 0%
17/10/20 09:55:54 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:54 INFO mapred.Task: Task:attempt_local809729497_0001_m_000069_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:55:54 INFO mapred.LocalJobRunner: map
17/10/20 09:55:54 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000069_0' done.
17/10/20 09:55:54 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00069_0
17/10/20 09:55:54 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0070_0
17/10/20 09:55:54 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:55:54 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:54 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:2785017856+33554432
17/10/20 09:55:54 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:54 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:54 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:54 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:54 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:54 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:55:54 INFO mapred.LocalJobRunner:
17/10/20 09:55:54 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:54 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:54 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:55:54 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:55:55 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:55 INFO mapred.Task: Task:attempt_local809729497_0001_m_000070_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:55:55 INFO mapred.LocalJobRunner: map
17/10/20 09:55:55 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000070_0' done.
17/10/20 09:55:55 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00070_0
17/10/20 09:55:55 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0071_0
17/10/20 09:55:55 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:55:55 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:55 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:2751463424+33554432
17/10/20 09:55:55 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:55 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:55 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:55 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:55 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:55 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:55:55 INFO mapreduce.Job:  map 100% reduce 0%
17/10/20 09:55:55 INFO mapred.LocalJobRunner:
17/10/20 09:55:55 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:55 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:55 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:55:55 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:55:56 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:56 INFO mapred.Task: Task:attempt_local809729497_0001_m_000071_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:55:56 INFO mapred.LocalJobRunner: map
17/10/20 09:55:56 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000071_0' done.
17/10/20 09:55:56 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00071_0
17/10/20 09:55:56 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0072_0
17/10/20 09:55:56 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:55:56 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:56 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:2717908992+33554432
17/10/20 09:55:56 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:56 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:56 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:56 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:56 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:56 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:55:56 INFO mapred.LocalJobRunner:
17/10/20 09:55:56 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:56 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:56 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/20 09:55:56 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(994888                                                                                                                         80); length = 1342177/6553600
17/10/20 09:55:56 INFO mapreduce.Job:  map 47% reduce 0%
17/10/20 09:55:57 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:57 INFO mapred.Task: Task:attempt_local809729497_0001_m_000072_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:55:57 INFO mapred.LocalJobRunner: map
17/10/20 09:55:57 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000072_0' done.
17/10/20 09:55:57 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00072_0
17/10/20 09:55:57 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0073_0
17/10/20 09:55:57 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:55:57 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:57 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:2684354560+33554432
17/10/20 09:55:57 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:57 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:57 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:57 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:57 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:57 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:55:57 INFO mapred.LocalJobRunner:
17/10/20 09:55:57 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:57 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:57 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:55:57 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:55:57 INFO mapreduce.Job:  map 48% reduce 0%
17/10/20 09:55:57 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:57 INFO mapred.Task: Task:attempt_local809729497_0001_m_000073_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:55:57 INFO mapred.LocalJobRunner: map
17/10/20 09:55:57 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000073_0' done.
17/10/20 09:55:57 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00073_0
17/10/20 09:55:57 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0074_0
17/10/20 09:55:57 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:55:57 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:57 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:2650800128+33554432
17/10/20 09:55:57 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:57 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:57 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:57 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:57 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:57 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:55:58 INFO mapred.LocalJobRunner:
17/10/20 09:55:58 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:58 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:58 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:55:58 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:55:58 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:58 INFO mapred.Task: Task:attempt_local809729497_0001_m_000074_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:55:58 INFO mapred.LocalJobRunner: map
17/10/20 09:55:58 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000074_0' done.
17/10/20 09:55:58 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00074_0
17/10/20 09:55:58 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0075_0
17/10/20 09:55:58 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:55:58 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:58 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:2617245696+33554432
17/10/20 09:55:58 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:58 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:58 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:58 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:58 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:58 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:55:58 INFO mapred.LocalJobRunner:
17/10/20 09:55:58 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:58 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:58 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/20 09:55:58 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(994888                                                                                                                         80); length = 1342177/6553600
17/10/20 09:55:59 INFO mapreduce.Job:  map 49% reduce 0%
17/10/20 09:55:59 INFO mapred.MapTask: Finished spill 0
17/10/20 09:55:59 INFO mapred.Task: Task:attempt_local809729497_0001_m_000075_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:55:59 INFO mapred.LocalJobRunner: map
17/10/20 09:55:59 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000075_0' done.
17/10/20 09:55:59 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00075_0
17/10/20 09:55:59 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0076_0
17/10/20 09:55:59 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:55:59 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:55:59 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:2583691264+33554432
17/10/20 09:55:59 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:55:59 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:55:59 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:55:59 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:55:59 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:55:59 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:55:59 INFO mapred.LocalJobRunner:
17/10/20 09:55:59 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:55:59 INFO mapred.MapTask: Spilling map output
17/10/20 09:55:59 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:55:59 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:56:00 INFO mapreduce.Job:  map 50% reduce 0%
17/10/20 09:56:00 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:00 INFO mapred.Task: Task:attempt_local809729497_0001_m_000076_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:00 INFO mapred.LocalJobRunner: map
17/10/20 09:56:00 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000076_0' done.
17/10/20 09:56:00 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00076_0
17/10/20 09:56:00 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0077_0
17/10/20 09:56:00 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:00 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:00 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:2550136832+33554432
17/10/20 09:56:00 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:00 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:00 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:00 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:00 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:00 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:00 INFO mapred.LocalJobRunner:
17/10/20 09:56:00 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:00 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:00 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:56:00 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:56:01 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:01 INFO mapred.Task: Task:attempt_local809729497_0001_m_000077_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:01 INFO mapred.LocalJobRunner: map
17/10/20 09:56:01 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000077_0' done.
17/10/20 09:56:01 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00077_0
17/10/20 09:56:01 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0078_0
17/10/20 09:56:01 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:01 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:01 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:2516582400+33554432
17/10/20 09:56:01 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:01 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:01 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:01 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:01 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:01 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:01 INFO mapreduce.Job:  map 100% reduce 0%
17/10/20 09:56:01 INFO mapred.LocalJobRunner:
17/10/20 09:56:01 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:01 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:01 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/20 09:56:01 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(994888                                                                                                                         80); length = 1342177/6553600
17/10/20 09:56:02 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:02 INFO mapred.Task: Task:attempt_local809729497_0001_m_000078_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:02 INFO mapred.LocalJobRunner: map
17/10/20 09:56:02 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000078_0' done.
17/10/20 09:56:02 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00078_0
17/10/20 09:56:02 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0079_0
17/10/20 09:56:02 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:02 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:02 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:2483027968+33554432
17/10/20 09:56:02 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:02 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:02 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:02 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:02 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:02 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:02 INFO mapred.LocalJobRunner:
17/10/20 09:56:02 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:02 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:02 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:56:02 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:56:02 INFO mapreduce.Job:  map 52% reduce 0%
17/10/20 09:56:02 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:02 INFO mapred.Task: Task:attempt_local809729497_0001_m_000079_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:02 INFO mapred.LocalJobRunner: map
17/10/20 09:56:02 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000079_0' done.
17/10/20 09:56:02 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00079_0
17/10/20 09:56:02 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0080_0
17/10/20 09:56:02 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:02 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:02 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:2449473536+33554432
17/10/20 09:56:02 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:02 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:02 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:02 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:02 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:02 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:03 INFO mapred.LocalJobRunner:
17/10/20 09:56:03 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:03 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:03 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:56:03 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:56:03 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:03 INFO mapred.Task: Task:attempt_local809729497_0001_m_000080_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:03 INFO mapred.LocalJobRunner: map
17/10/20 09:56:03 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000080_0' done.
17/10/20 09:56:03 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00080_0
17/10/20 09:56:03 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0081_0
17/10/20 09:56:03 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:03 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:03 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:2415919104+33554432
17/10/20 09:56:03 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:03 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:03 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:03 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:03 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:03 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:04 INFO mapred.LocalJobRunner:
17/10/20 09:56:04 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:04 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:04 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:56:04 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:56:04 INFO mapreduce.Job:  map 53% reduce 0%
17/10/20 09:56:04 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:04 INFO mapred.Task: Task:attempt_local809729497_0001_m_000081_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:04 INFO mapred.LocalJobRunner: map
17/10/20 09:56:04 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000081_0' done.
17/10/20 09:56:04 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00081_0
17/10/20 09:56:04 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0082_0
17/10/20 09:56:04 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:04 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:04 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:2382364672+33554432
17/10/20 09:56:04 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:04 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:04 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:04 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:04 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:04 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:04 INFO mapred.LocalJobRunner:
17/10/20 09:56:04 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:04 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:04 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/20 09:56:04 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(994888                                                                                                                         80); length = 1342177/6553600
17/10/20 09:56:05 INFO mapreduce.Job:  map 54% reduce 0%
17/10/20 09:56:05 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:05 INFO mapred.Task: Task:attempt_local809729497_0001_m_000082_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:05 INFO mapred.LocalJobRunner: map
17/10/20 09:56:05 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000082_0' done.
17/10/20 09:56:05 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00082_0
17/10/20 09:56:05 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0083_0
17/10/20 09:56:05 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:05 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:05 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:2348810240+33554432
17/10/20 09:56:05 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:05 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:05 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:05 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:05 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:05 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:05 INFO mapred.LocalJobRunner:
17/10/20 09:56:05 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:05 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:05 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:56:05 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:56:06 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:06 INFO mapred.Task: Task:attempt_local809729497_0001_m_000083_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:06 INFO mapred.LocalJobRunner: map
17/10/20 09:56:06 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000083_0' done.
17/10/20 09:56:06 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00083_0
17/10/20 09:56:06 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0084_0
17/10/20 09:56:06 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:06 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:06 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:2315255808+33554432
17/10/20 09:56:06 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:06 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:06 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:06 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:06 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:06 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:06 INFO mapred.LocalJobRunner:
17/10/20 09:56:06 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:06 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:06 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:56:06 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:56:07 INFO mapreduce.Job:  map 55% reduce 0%
17/10/20 09:56:07 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:07 INFO mapred.Task: Task:attempt_local809729497_0001_m_000084_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:07 INFO mapred.LocalJobRunner: map
17/10/20 09:56:07 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000084_0' done.
17/10/20 09:56:07 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00084_0
17/10/20 09:56:07 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0085_0
17/10/20 09:56:07 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:07 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:07 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:2281701376+33554432
17/10/20 09:56:07 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:07 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:07 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:07 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:07 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:07 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:07 INFO mapred.LocalJobRunner:
17/10/20 09:56:07 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:07 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:07 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/20 09:56:07 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(994888                                                                                                                         80); length = 1342177/6553600
17/10/20 09:56:08 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:08 INFO mapred.Task: Task:attempt_local809729497_0001_m_000085_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:08 INFO mapred.LocalJobRunner: map
17/10/20 09:56:08 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000085_0' done.
17/10/20 09:56:08 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00085_0
17/10/20 09:56:08 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0086_0
17/10/20 09:56:08 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:08 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:08 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:2248146944+33554432
17/10/20 09:56:08 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:08 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:08 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:08 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:08 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:08 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:08 INFO mapreduce.Job:  map 100% reduce 0%
17/10/20 09:56:08 INFO mapred.LocalJobRunner:
17/10/20 09:56:08 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:08 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:08 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:56:08 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:56:09 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:09 INFO mapred.Task: Task:attempt_local809729497_0001_m_000086_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:09 INFO mapred.LocalJobRunner: map
17/10/20 09:56:09 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000086_0' done.
17/10/20 09:56:09 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00086_0
17/10/20 09:56:09 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0087_0
17/10/20 09:56:09 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:09 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:09 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:2214592512+33554432
17/10/20 09:56:09 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:09 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:09 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:09 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:09 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:09 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:09 INFO mapred.LocalJobRunner:
17/10/20 09:56:09 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:09 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:09 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:56:09 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:56:10 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:10 INFO mapred.Task: Task:attempt_local809729497_0001_m_000087_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:10 INFO mapred.LocalJobRunner: map
17/10/20 09:56:10 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000087_0' done.
17/10/20 09:56:10 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00087_0
17/10/20 09:56:10 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0088_0
17/10/20 09:56:10 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:10 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:10 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:2181038080+33554432
17/10/20 09:56:10 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:10 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:10 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:10 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:10 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:10 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:10 INFO mapred.LocalJobRunner:
17/10/20 09:56:10 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:10 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:10 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/20 09:56:10 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(994888                                                                                                                         80); length = 1342177/6553600
17/10/20 09:56:11 INFO mapreduce.Job:  map 58% reduce 0%
17/10/20 09:56:11 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:11 INFO mapred.Task: Task:attempt_local809729497_0001_m_000088_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:11 INFO mapred.LocalJobRunner: map
17/10/20 09:56:11 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000088_0' done.
17/10/20 09:56:11 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00088_0
17/10/20 09:56:11 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0089_0
17/10/20 09:56:11 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:11 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:11 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:2147483648+33554432
17/10/20 09:56:11 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:11 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:11 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:11 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:11 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:11 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:11 INFO mapred.LocalJobRunner:
17/10/20 09:56:11 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:11 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:11 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:56:11 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:56:12 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:12 INFO mapred.Task: Task:attempt_local809729497_0001_m_000089_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:12 INFO mapred.LocalJobRunner: map
17/10/20 09:56:12 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000089_0' done.
17/10/20 09:56:12 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00089_0
17/10/20 09:56:12 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0090_0
17/10/20 09:56:12 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:12 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:12 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:2113929216+33554432
17/10/20 09:56:12 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:12 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:12 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:12 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:12 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:12 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:12 INFO mapred.LocalJobRunner:
17/10/20 09:56:12 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:12 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:12 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:56:12 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:56:13 INFO mapreduce.Job:  map 59% reduce 0%
17/10/20 09:56:13 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:13 INFO mapred.Task: Task:attempt_local809729497_0001_m_000090_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:13 INFO mapred.LocalJobRunner: map
17/10/20 09:56:13 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000090_0' done.
17/10/20 09:56:13 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00090_0
17/10/20 09:56:13 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0091_0
17/10/20 09:56:13 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:13 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:13 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:2080374784+33554432
17/10/20 09:56:13 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:13 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:13 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:13 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:13 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:13 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:13 INFO mapred.LocalJobRunner:
17/10/20 09:56:13 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:13 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:13 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/20 09:56:13 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(994888                                                                                                                         80); length = 1342177/6553600
17/10/20 09:56:14 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:14 INFO mapred.Task: Task:attempt_local809729497_0001_m_000091_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:14 INFO mapred.LocalJobRunner: map
17/10/20 09:56:14 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000091_0' done.
17/10/20 09:56:14 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00091_0
17/10/20 09:56:14 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0092_0
17/10/20 09:56:14 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:14 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:14 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:2046820352+33554432
17/10/20 09:56:14 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:14 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:14 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:14 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:14 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:14 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:14 INFO mapred.LocalJobRunner:
17/10/20 09:56:14 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:14 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:14 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:56:14 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:56:15 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:15 INFO mapred.Task: Task:attempt_local809729497_0001_m_000092_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:15 INFO mapred.LocalJobRunner: map
17/10/20 09:56:15 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000092_0' done.
17/10/20 09:56:15 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00092_0
17/10/20 09:56:15 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0093_0
17/10/20 09:56:15 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:15 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:15 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:2013265920+33554432
17/10/20 09:56:15 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:15 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:15 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:15 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:15 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:15 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:15 INFO mapreduce.Job:  map 100% reduce 0%
17/10/20 09:56:15 INFO mapred.LocalJobRunner:
17/10/20 09:56:15 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:15 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:15 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:56:15 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:56:16 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:16 INFO mapred.Task: Task:attempt_local809729497_0001_m_000093_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:16 INFO mapred.LocalJobRunner: map
17/10/20 09:56:16 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000093_0' done.
17/10/20 09:56:16 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00093_0
17/10/20 09:56:16 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0094_0
17/10/20 09:56:16 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:16 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:16 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:1979711488+33554432
17/10/20 09:56:16 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:16 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:16 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:16 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:16 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:16 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:16 INFO mapred.LocalJobRunner:
17/10/20 09:56:16 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:16 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:16 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/20 09:56:16 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(994888                                                                                                                         80); length = 1342177/6553600
17/10/20 09:56:16 INFO mapreduce.Job:  map 61% reduce 0%
17/10/20 09:56:16 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:16 INFO mapred.Task: Task:attempt_local809729497_0001_m_000094_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:16 INFO mapred.LocalJobRunner: map
17/10/20 09:56:16 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000094_0' done.
17/10/20 09:56:16 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00094_0
17/10/20 09:56:16 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0095_0
17/10/20 09:56:16 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:16 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:16 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:1946157056+33554432
17/10/20 09:56:16 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:16 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:16 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:16 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:16 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:16 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:17 INFO mapred.LocalJobRunner:
17/10/20 09:56:17 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:17 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:17 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:56:17 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:56:17 INFO mapreduce.Job:  map 62% reduce 0%
17/10/20 09:56:17 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:17 INFO mapred.Task: Task:attempt_local809729497_0001_m_000095_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:17 INFO mapred.LocalJobRunner: map
17/10/20 09:56:17 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000095_0' done.
17/10/20 09:56:17 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00095_0
17/10/20 09:56:17 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0096_0
17/10/20 09:56:17 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:17 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:17 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:1912602624+33554432
17/10/20 09:56:17 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:17 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:17 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:17 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:17 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:17 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:17 INFO mapred.LocalJobRunner:
17/10/20 09:56:17 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:17 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:17 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:56:17 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:56:18 INFO mapreduce.Job:  map 63% reduce 0%
17/10/20 09:56:18 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:18 INFO mapred.Task: Task:attempt_local809729497_0001_m_000096_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:18 INFO mapred.LocalJobRunner: map
17/10/20 09:56:18 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000096_0' done.
17/10/20 09:56:18 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00096_0
17/10/20 09:56:18 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0097_0
17/10/20 09:56:18 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:18 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:18 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:1879048192+33554432
17/10/20 09:56:18 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:18 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:18 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:18 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:18 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:18 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:18 INFO mapred.LocalJobRunner:
17/10/20 09:56:18 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:18 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:18 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/20 09:56:18 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(994888                                                                                                                         80); length = 1342177/6553600
17/10/20 09:56:19 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:19 INFO mapred.Task: Task:attempt_local809729497_0001_m_000097_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:19 INFO mapred.LocalJobRunner: map
17/10/20 09:56:19 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000097_0' done.
17/10/20 09:56:19 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00097_0
17/10/20 09:56:19 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0098_0
17/10/20 09:56:19 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:19 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:19 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:1845493760+33554432
17/10/20 09:56:19 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:19 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:19 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:19 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:19 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:19 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:19 INFO mapred.LocalJobRunner:
17/10/20 09:56:19 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:19 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:19 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:56:19 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:56:20 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:20 INFO mapred.Task: Task:attempt_local809729497_0001_m_000098_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:20 INFO mapred.LocalJobRunner: map
17/10/20 09:56:20 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000098_0' done.
17/10/20 09:56:20 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00098_0
17/10/20 09:56:20 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0099_0
17/10/20 09:56:20 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:20 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:20 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:1811939328+33554432
17/10/20 09:56:20 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:20 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:20 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:20 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:20 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:20 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:20 INFO mapreduce.Job:  map 100% reduce 0%
17/10/20 09:56:20 INFO mapred.LocalJobRunner:
17/10/20 09:56:20 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:20 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:20 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:56:20 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:56:21 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:21 INFO mapred.Task: Task:attempt_local809729497_0001_m_000099_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:21 INFO mapred.LocalJobRunner: map
17/10/20 09:56:21 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000099_0' done.
17/10/20 09:56:21 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00099_0
17/10/20 09:56:21 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0100_0
17/10/20 09:56:21 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:21 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:21 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:1778384896+33554432
17/10/20 09:56:21 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:21 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:21 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:21 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:21 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:21 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:21 INFO mapred.LocalJobRunner:
17/10/20 09:56:21 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:21 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:21 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/20 09:56:21 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(994888                                                                                                                         80); length = 1342177/6553600
17/10/20 09:56:21 INFO mapreduce.Job:  map 65% reduce 0%
17/10/20 09:56:22 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:22 INFO mapred.Task: Task:attempt_local809729497_0001_m_000100_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:22 INFO mapred.LocalJobRunner: map
17/10/20 09:56:22 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000100_0' done.
17/10/20 09:56:22 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00100_0
17/10/20 09:56:22 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0101_0
17/10/20 09:56:22 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:22 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:22 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:1744830464+33554432
17/10/20 09:56:22 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:22 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:22 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:22 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:22 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:22 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:22 INFO mapred.LocalJobRunner:
17/10/20 09:56:22 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:22 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:22 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:56:22 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:56:22 INFO mapreduce.Job:  map 66% reduce 0%
17/10/20 09:56:22 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:22 INFO mapred.Task: Task:attempt_local809729497_0001_m_000101_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:22 INFO mapred.LocalJobRunner: map
17/10/20 09:56:22 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000101_0' done.
17/10/20 09:56:22 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00101_0
17/10/20 09:56:22 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0102_0
17/10/20 09:56:22 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:22 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:22 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:1711276032+33554432
17/10/20 09:56:22 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:22 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:22 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:22 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:22 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:22 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:23 INFO mapred.LocalJobRunner:
17/10/20 09:56:23 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:23 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:23 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:56:23 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:56:23 INFO mapreduce.Job:  map 67% reduce 0%
17/10/20 09:56:23 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:23 INFO mapred.Task: Task:attempt_local809729497_0001_m_000102_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:23 INFO mapred.LocalJobRunner: map
17/10/20 09:56:23 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000102_0' done.
17/10/20 09:56:23 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00102_0
17/10/20 09:56:23 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0103_0
17/10/20 09:56:23 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:23 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:23 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:1677721600+33554432
17/10/20 09:56:23 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:23 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:23 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:23 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:23 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:23 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:23 INFO mapred.LocalJobRunner:
17/10/20 09:56:23 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:23 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:23 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/20 09:56:23 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(994888                                                                                                                         80); length = 1342177/6553600
17/10/20 09:56:24 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:24 INFO mapred.Task: Task:attempt_local809729497_0001_m_000103_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:24 INFO mapred.LocalJobRunner: map
17/10/20 09:56:24 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000103_0' done.
17/10/20 09:56:24 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00103_0
17/10/20 09:56:24 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0104_0
17/10/20 09:56:24 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:24 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:24 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:1644167168+33554432
17/10/20 09:56:24 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:24 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:24 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:24 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:24 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:24 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:24 INFO mapred.LocalJobRunner:
17/10/20 09:56:24 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:24 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:24 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:56:24 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:56:25 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:25 INFO mapred.Task: Task:attempt_local809729497_0001_m_000104_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:25 INFO mapred.LocalJobRunner: map
17/10/20 09:56:25 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000104_0' done.
17/10/20 09:56:25 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00104_0
17/10/20 09:56:25 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0105_0
17/10/20 09:56:25 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:25 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:25 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:1610612736+33554432
17/10/20 09:56:25 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:25 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:25 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:25 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:25 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:25 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:25 INFO mapreduce.Job:  map 100% reduce 0%
17/10/20 09:56:25 INFO mapred.LocalJobRunner:
17/10/20 09:56:25 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:25 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:25 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:56:25 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:56:26 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:26 INFO mapred.Task: Task:attempt_local809729497_0001_m_000105_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:26 INFO mapred.LocalJobRunner: map
17/10/20 09:56:26 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000105_0' done.
17/10/20 09:56:26 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00105_0
17/10/20 09:56:26 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0106_0
17/10/20 09:56:26 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:26 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:26 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:1577058304+33554432
17/10/20 09:56:26 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:26 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:26 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:26 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:26 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:26 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:26 INFO mapred.LocalJobRunner:
17/10/20 09:56:26 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:26 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:26 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:56:26 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:56:27 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:27 INFO mapred.Task: Task:attempt_local809729497_0001_m_000106_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:27 INFO mapred.LocalJobRunner: map
17/10/20 09:56:27 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000106_0' done.
17/10/20 09:56:27 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00106_0
17/10/20 09:56:27 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0107_0
17/10/20 09:56:27 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:27 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:27 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:1543503872+33554432
17/10/20 09:56:27 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:27 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:27 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:27 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:27 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:27 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:27 INFO mapred.LocalJobRunner:
17/10/20 09:56:27 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:27 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:27 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/20 09:56:27 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(994888                                                                                                                         80); length = 1342177/6553600
17/10/20 09:56:27 INFO mapreduce.Job:  map 70% reduce 0%
17/10/20 09:56:28 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:28 INFO mapred.Task: Task:attempt_local809729497_0001_m_000107_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:28 INFO mapred.LocalJobRunner: map
17/10/20 09:56:28 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000107_0' done.
17/10/20 09:56:28 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00107_0
17/10/20 09:56:28 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0108_0
17/10/20 09:56:28 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:28 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:28 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:1509949440+33554432
17/10/20 09:56:28 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:28 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:28 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:28 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:28 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:28 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:28 INFO mapred.LocalJobRunner:
17/10/20 09:56:28 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:28 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:28 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:56:28 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:56:28 INFO mapreduce.Job:  map 71% reduce 0%
17/10/20 09:56:28 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:28 INFO mapred.Task: Task:attempt_local809729497_0001_m_000108_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:28 INFO mapred.LocalJobRunner: map
17/10/20 09:56:28 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000108_0' done.
17/10/20 09:56:28 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00108_0
17/10/20 09:56:28 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0109_0
17/10/20 09:56:28 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:28 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:28 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:1476395008+33554432
17/10/20 09:56:28 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:28 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:28 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:28 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:28 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:28 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:29 INFO mapred.LocalJobRunner:
17/10/20 09:56:29 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:29 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:29 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:56:29 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:56:29 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:29 INFO mapred.Task: Task:attempt_local809729497_0001_m_000109_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:29 INFO mapred.LocalJobRunner: map
17/10/20 09:56:29 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000109_0' done.
17/10/20 09:56:29 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00109_0
17/10/20 09:56:29 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0110_0
17/10/20 09:56:29 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:29 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:29 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:1442840576+33554432
17/10/20 09:56:29 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:29 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:29 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:29 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:29 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:29 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:29 INFO mapred.LocalJobRunner:
17/10/20 09:56:29 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:29 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:29 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/20 09:56:29 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(994888                                                                                                                         80); length = 1342177/6553600
17/10/20 09:56:30 INFO mapreduce.Job:  map 72% reduce 0%
17/10/20 09:56:30 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:30 INFO mapred.Task: Task:attempt_local809729497_0001_m_000110_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:30 INFO mapred.LocalJobRunner: map
17/10/20 09:56:30 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000110_0' done.
17/10/20 09:56:30 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00110_0
17/10/20 09:56:30 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0111_0
17/10/20 09:56:30 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:30 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:30 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:1409286144+33554432
17/10/20 09:56:30 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:30 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:30 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:30 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:30 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:30 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:30 INFO mapred.LocalJobRunner:
17/10/20 09:56:30 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:30 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:30 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:56:30 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:56:31 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:31 INFO mapred.Task: Task:attempt_local809729497_0001_m_000111_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:31 INFO mapred.LocalJobRunner: map
17/10/20 09:56:31 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000111_0' done.
17/10/20 09:56:31 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00111_0
17/10/20 09:56:31 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0112_0
17/10/20 09:56:31 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:31 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:31 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:1375731712+33554432
17/10/20 09:56:31 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:31 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:31 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:31 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:31 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:31 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:31 INFO mapreduce.Job:  map 100% reduce 0%
17/10/20 09:56:31 INFO mapred.LocalJobRunner:
17/10/20 09:56:31 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:31 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:31 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:56:31 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:56:32 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:32 INFO mapred.Task: Task:attempt_local809729497_0001_m_000112_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:32 INFO mapred.LocalJobRunner: map
17/10/20 09:56:32 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000112_0' done.
17/10/20 09:56:32 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00112_0
17/10/20 09:56:32 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0113_0
17/10/20 09:56:32 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:32 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:32 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:1342177280+33554432
17/10/20 09:56:32 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:32 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:32 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:32 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:32 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:32 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:32 INFO mapred.LocalJobRunner:
17/10/20 09:56:32 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:32 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:32 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/20 09:56:32 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(994888                                                                                                                         80); length = 1342177/6553600
17/10/20 09:56:32 INFO mapreduce.Job:  map 74% reduce 0%
17/10/20 09:56:33 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:33 INFO mapred.Task: Task:attempt_local809729497_0001_m_000113_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:33 INFO mapred.LocalJobRunner: map
17/10/20 09:56:33 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000113_0' done.
17/10/20 09:56:33 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00113_0
17/10/20 09:56:33 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0114_0
17/10/20 09:56:33 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:33 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:33 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:1308622848+33554432
17/10/20 09:56:33 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:33 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:33 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:33 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:33 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:33 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:33 INFO mapred.LocalJobRunner:
17/10/20 09:56:33 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:33 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:33 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:56:33 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:56:33 INFO mapreduce.Job:  map 75% reduce 0%
17/10/20 09:56:34 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:34 INFO mapred.Task: Task:attempt_local809729497_0001_m_000114_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:34 INFO mapred.LocalJobRunner: map
17/10/20 09:56:34 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000114_0' done.
17/10/20 09:56:34 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00114_0
17/10/20 09:56:34 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0115_0
17/10/20 09:56:34 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:34 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:34 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:1275068416+33554432
17/10/20 09:56:34 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:34 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:34 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:34 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:34 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:34 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:34 INFO mapred.LocalJobRunner:
17/10/20 09:56:34 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:34 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:34 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:56:34 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:56:34 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:34 INFO mapred.Task: Task:attempt_local809729497_0001_m_000115_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:34 INFO mapred.LocalJobRunner: map
17/10/20 09:56:34 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000115_0' done.
17/10/20 09:56:34 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00115_0
17/10/20 09:56:34 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0116_0
17/10/20 09:56:34 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:34 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:34 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:1241513984+33554432
17/10/20 09:56:34 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:34 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:34 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:34 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:34 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:34 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:35 INFO mapred.LocalJobRunner:
17/10/20 09:56:35 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:35 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:35 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/20 09:56:35 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(994888                                                                                                                         80); length = 1342177/6553600
17/10/20 09:56:35 INFO mapreduce.Job:  map 76% reduce 0%
17/10/20 09:56:35 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:35 INFO mapred.Task: Task:attempt_local809729497_0001_m_000116_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:35 INFO mapred.LocalJobRunner: map
17/10/20 09:56:35 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000116_0' done.
17/10/20 09:56:35 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00116_0
17/10/20 09:56:35 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0117_0
17/10/20 09:56:35 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:35 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:35 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:1207959552+33554432
17/10/20 09:56:35 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:35 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:35 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:35 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:35 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:35 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:35 INFO mapred.LocalJobRunner:
17/10/20 09:56:35 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:35 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:35 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:56:35 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:56:36 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:36 INFO mapred.Task: Task:attempt_local809729497_0001_m_000117_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:36 INFO mapred.LocalJobRunner: map
17/10/20 09:56:36 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000117_0' done.
17/10/20 09:56:36 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00117_0
17/10/20 09:56:36 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0118_0
17/10/20 09:56:36 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:36 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:36 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:1174405120+33554432
17/10/20 09:56:36 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:36 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:36 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:36 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:36 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:36 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:36 INFO mapred.LocalJobRunner:
17/10/20 09:56:36 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:36 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:36 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:56:36 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:56:37 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:37 INFO mapred.Task: Task:attempt_local809729497_0001_m_000118_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:37 INFO mapred.LocalJobRunner: map
17/10/20 09:56:37 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000118_0' done.
17/10/20 09:56:37 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00118_0
17/10/20 09:56:37 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0119_0
17/10/20 09:56:37 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:37 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:37 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:1140850688+33554432
17/10/20 09:56:37 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:37 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:37 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:37 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:37 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:37 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:37 INFO mapreduce.Job:  map 100% reduce 0%
17/10/20 09:56:37 INFO mapred.LocalJobRunner:
17/10/20 09:56:37 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:37 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:37 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/20 09:56:37 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(994888                                                                                                                         80); length = 1342177/6553600
17/10/20 09:56:38 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:38 INFO mapred.Task: Task:attempt_local809729497_0001_m_000119_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:38 INFO mapred.LocalJobRunner: map
17/10/20 09:56:38 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000119_0' done.
17/10/20 09:56:38 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00119_0
17/10/20 09:56:38 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0120_0
17/10/20 09:56:38 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:38 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:38 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:1107296256+33554432
17/10/20 09:56:38 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:38 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:38 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:38 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:38 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:38 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:38 INFO mapred.LocalJobRunner:
17/10/20 09:56:38 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:38 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:38 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:56:38 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:56:38 INFO mapreduce.Job:  map 78% reduce 0%
17/10/20 09:56:39 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:39 INFO mapred.Task: Task:attempt_local809729497_0001_m_000120_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:39 INFO mapred.LocalJobRunner: map
17/10/20 09:56:39 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000120_0' done.
17/10/20 09:56:39 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00120_0
17/10/20 09:56:39 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0121_0
17/10/20 09:56:39 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:39 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:39 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:1073741824+33554432
17/10/20 09:56:39 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:39 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:39 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:39 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:39 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:39 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:39 INFO mapred.LocalJobRunner:
17/10/20 09:56:39 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:39 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:39 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:56:39 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:56:39 INFO mapreduce.Job:  map 79% reduce 0%
17/10/20 09:56:39 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:39 INFO mapred.Task: Task:attempt_local809729497_0001_m_000121_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:39 INFO mapred.LocalJobRunner: map
17/10/20 09:56:39 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000121_0' done.
17/10/20 09:56:39 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00121_0
17/10/20 09:56:39 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0122_0
17/10/20 09:56:39 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:39 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:39 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:1040187392+33554432
17/10/20 09:56:39 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:39 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:39 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:39 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:39 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:39 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:40 INFO mapred.LocalJobRunner:
17/10/20 09:56:40 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:40 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:40 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/20 09:56:40 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(994888                                                                                                                         80); length = 1342177/6553600
17/10/20 09:56:40 INFO mapreduce.Job:  map 80% reduce 0%
17/10/20 09:56:40 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:40 INFO mapred.Task: Task:attempt_local809729497_0001_m_000122_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:40 INFO mapred.LocalJobRunner: map
17/10/20 09:56:40 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000122_0' done.
17/10/20 09:56:40 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00122_0
17/10/20 09:56:40 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0123_0
17/10/20 09:56:40 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:40 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:40 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:1006632960+33554432
17/10/20 09:56:40 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:40 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:40 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:40 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:40 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:40 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:40 INFO mapred.LocalJobRunner:
17/10/20 09:56:40 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:40 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:40 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:56:40 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:56:41 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:42 INFO mapred.Task: Task:attempt_local809729497_0001_m_000123_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:42 INFO mapred.LocalJobRunner: map
17/10/20 09:56:42 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000123_0' done.
17/10/20 09:56:42 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00123_0
17/10/20 09:56:42 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0124_0
17/10/20 09:56:42 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:42 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:42 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:973078528+33554432
17/10/20 09:56:42 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:42 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:42 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:42 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:42 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:42 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:42 INFO mapred.LocalJobRunner:
17/10/20 09:56:42 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:42 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:42 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:56:42 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:56:42 INFO mapreduce.Job:  map 81% reduce 0%
17/10/20 09:56:43 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:43 INFO mapred.Task: Task:attempt_local809729497_0001_m_000124_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:43 INFO mapred.LocalJobRunner: map
17/10/20 09:56:43 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000124_0' done.
17/10/20 09:56:43 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00124_0
17/10/20 09:56:43 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0125_0
17/10/20 09:56:43 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:43 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:43 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:939524096+33554432
17/10/20 09:56:43 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:43 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:43 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:43 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:43 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:43 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:43 INFO mapred.LocalJobRunner:
17/10/20 09:56:43 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:43 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:43 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/20 09:56:43 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(994888                                                                                                                         80); length = 1342177/6553600
17/10/20 09:56:43 INFO mapreduce.Job:  map 82% reduce 0%
17/10/20 09:56:44 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:44 INFO mapred.Task: Task:attempt_local809729497_0001_m_000125_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:44 INFO mapred.LocalJobRunner: map
17/10/20 09:56:44 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000125_0' done.
17/10/20 09:56:44 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00125_0
17/10/20 09:56:44 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0126_0
17/10/20 09:56:44 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:44 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:44 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:905969664+33554432
17/10/20 09:56:44 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:44 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:44 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:44 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:44 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:44 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:44 INFO mapred.LocalJobRunner:
17/10/20 09:56:44 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:44 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:44 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:56:44 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:56:44 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:44 INFO mapred.Task: Task:attempt_local809729497_0001_m_000126_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:44 INFO mapred.LocalJobRunner: map
17/10/20 09:56:44 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000126_0' done.
17/10/20 09:56:44 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00126_0
17/10/20 09:56:44 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0127_0
17/10/20 09:56:44 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:44 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:44 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:872415232+33554432
17/10/20 09:56:44 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:44 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:44 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:44 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:44 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:44 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:45 INFO mapred.LocalJobRunner:
17/10/20 09:56:45 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:45 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:45 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:56:45 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:56:45 INFO mapreduce.Job:  map 83% reduce 0%
17/10/20 09:56:45 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:45 INFO mapred.Task: Task:attempt_local809729497_0001_m_000127_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:45 INFO mapred.LocalJobRunner: map
17/10/20 09:56:45 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000127_0' done.
17/10/20 09:56:45 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00127_0
17/10/20 09:56:45 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0128_0
17/10/20 09:56:45 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:45 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:45 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:838860800+33554432
17/10/20 09:56:45 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:45 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:45 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:45 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:45 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:45 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:45 INFO mapred.LocalJobRunner:
17/10/20 09:56:45 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:45 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:45 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/20 09:56:45 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(994888                                                                                                                         80); length = 1342177/6553600
17/10/20 09:56:46 INFO mapreduce.Job:  map 84% reduce 0%
17/10/20 09:56:46 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:46 INFO mapred.Task: Task:attempt_local809729497_0001_m_000128_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:46 INFO mapred.LocalJobRunner: map
17/10/20 09:56:46 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000128_0' done.
17/10/20 09:56:46 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00128_0
17/10/20 09:56:46 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0129_0
17/10/20 09:56:46 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:46 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:46 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:805306368+33554432
17/10/20 09:56:46 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:46 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:46 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:46 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:46 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:46 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:46 INFO mapred.LocalJobRunner:
17/10/20 09:56:46 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:46 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:46 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:56:46 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:56:47 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:47 INFO mapred.Task: Task:attempt_local809729497_0001_m_000129_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:47 INFO mapred.LocalJobRunner: map
17/10/20 09:56:47 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000129_0' done.
17/10/20 09:56:47 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00129_0
17/10/20 09:56:47 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0130_0
17/10/20 09:56:47 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:47 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:47 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:771751936+33554432
17/10/20 09:56:47 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:47 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:47 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:47 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:47 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:47 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:47 INFO mapred.LocalJobRunner:
17/10/20 09:56:47 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:47 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:47 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:56:47 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:56:48 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:48 INFO mapred.Task: Task:attempt_local809729497_0001_m_000130_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:48 INFO mapred.LocalJobRunner: map
17/10/20 09:56:48 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000130_0' done.
17/10/20 09:56:48 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00130_0
17/10/20 09:56:48 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0131_0
17/10/20 09:56:48 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:48 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:48 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:738197504+33554432
17/10/20 09:56:48 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:48 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:48 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:48 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:48 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:48 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:48 INFO mapreduce.Job:  map 100% reduce 0%
17/10/20 09:56:48 INFO mapred.LocalJobRunner:
17/10/20 09:56:48 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:48 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:48 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:56:48 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:56:49 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:49 INFO mapred.Task: Task:attempt_local809729497_0001_m_000131_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:49 INFO mapred.LocalJobRunner: map
17/10/20 09:56:49 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000131_0' done.
17/10/20 09:56:49 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00131_0
17/10/20 09:56:49 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0132_0
17/10/20 09:56:49 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:49 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:49 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:704643072+33554432
17/10/20 09:56:49 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:49 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:49 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:49 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:49 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:49 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:49 INFO mapred.LocalJobRunner:
17/10/20 09:56:49 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:49 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:49 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/20 09:56:49 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(994888                                                                                                                         80); length = 1342177/6553600
17/10/20 09:56:49 INFO mapreduce.Job:  map 86% reduce 0%
17/10/20 09:56:50 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:50 INFO mapred.Task: Task:attempt_local809729497_0001_m_000132_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:50 INFO mapred.LocalJobRunner: map
17/10/20 09:56:50 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000132_0' done.
17/10/20 09:56:50 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00132_0
17/10/20 09:56:50 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0133_0
17/10/20 09:56:50 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:50 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:50 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:671088640+33554432
17/10/20 09:56:50 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:50 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:50 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:50 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:50 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:50 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:50 INFO mapred.LocalJobRunner:
17/10/20 09:56:50 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:50 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:50 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:56:50 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:56:50 INFO mapreduce.Job:  map 87% reduce 0%
17/10/20 09:56:50 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:50 INFO mapred.Task: Task:attempt_local809729497_0001_m_000133_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:50 INFO mapred.LocalJobRunner: map
17/10/20 09:56:50 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000133_0' done.
17/10/20 09:56:50 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00133_0
17/10/20 09:56:50 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0134_0
17/10/20 09:56:50 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:50 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:50 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:637534208+33554432
17/10/20 09:56:50 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:50 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:50 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:50 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:50 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:50 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:51 INFO mapred.LocalJobRunner:
17/10/20 09:56:51 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:51 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:51 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:56:51 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:56:51 INFO mapreduce.Job:  map 88% reduce 0%
17/10/20 09:56:51 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:51 INFO mapred.Task: Task:attempt_local809729497_0001_m_000134_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:51 INFO mapred.LocalJobRunner: map
17/10/20 09:56:51 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000134_0' done.
17/10/20 09:56:51 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00134_0
17/10/20 09:56:51 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0135_0
17/10/20 09:56:51 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:51 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:51 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:603979776+33554432
17/10/20 09:56:51 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:51 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:51 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:51 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:51 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:51 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:51 INFO mapred.LocalJobRunner:
17/10/20 09:56:51 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:51 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:51 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/20 09:56:51 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(994888                                                                                                                         80); length = 1342177/6553600
17/10/20 09:56:52 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:52 INFO mapred.Task: Task:attempt_local809729497_0001_m_000135_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:52 INFO mapred.LocalJobRunner: map
17/10/20 09:56:52 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000135_0' done.
17/10/20 09:56:52 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00135_0
17/10/20 09:56:52 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0136_0
17/10/20 09:56:52 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:52 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:52 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:570425344+33554432
17/10/20 09:56:52 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:52 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:52 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:52 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:52 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:52 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:52 INFO mapred.LocalJobRunner:
17/10/20 09:56:52 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:52 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:52 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:56:52 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:56:53 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:53 INFO mapred.Task: Task:attempt_local809729497_0001_m_000136_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:53 INFO mapred.LocalJobRunner: map
17/10/20 09:56:53 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000136_0' done.
17/10/20 09:56:53 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00136_0
17/10/20 09:56:53 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0137_0
17/10/20 09:56:53 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:53 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:53 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:536870912+33554432
17/10/20 09:56:53 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:53 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:53 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:53 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:53 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:53 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:53 INFO mapreduce.Job:  map 100% reduce 0%
17/10/20 09:56:53 INFO mapred.LocalJobRunner:
17/10/20 09:56:53 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:53 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:53 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:56:53 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:56:54 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:54 INFO mapred.Task: Task:attempt_local809729497_0001_m_000137_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:54 INFO mapred.LocalJobRunner: map
17/10/20 09:56:54 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000137_0' done.
17/10/20 09:56:54 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00137_0
17/10/20 09:56:54 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0138_0
17/10/20 09:56:54 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:54 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:54 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:503316480+33554432
17/10/20 09:56:54 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:54 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:54 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:54 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:54 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:54 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:54 INFO mapred.LocalJobRunner:
17/10/20 09:56:54 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:54 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:54 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/20 09:56:54 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(994888                                                                                                                         80); length = 1342177/6553600
17/10/20 09:56:54 INFO mapreduce.Job:  map 90% reduce 0%
17/10/20 09:56:55 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:55 INFO mapred.Task: Task:attempt_local809729497_0001_m_000138_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:55 INFO mapred.LocalJobRunner: map
17/10/20 09:56:55 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000138_0' done.
17/10/20 09:56:55 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00138_0
17/10/20 09:56:55 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0139_0
17/10/20 09:56:55 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:55 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:55 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:469762048+33554432
17/10/20 09:56:55 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:55 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:55 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:55 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:55 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:55 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:55 INFO mapred.LocalJobRunner:
17/10/20 09:56:55 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:55 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:55 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:56:55 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:56:55 INFO mapreduce.Job:  map 91% reduce 0%
17/10/20 09:56:55 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:55 INFO mapred.Task: Task:attempt_local809729497_0001_m_000139_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:55 INFO mapred.LocalJobRunner: map
17/10/20 09:56:55 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000139_0' done.
17/10/20 09:56:55 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00139_0
17/10/20 09:56:55 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0140_0
17/10/20 09:56:55 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:55 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:55 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:436207616+33554432
17/10/20 09:56:55 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:55 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:55 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:55 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:55 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:55 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:56 INFO mapred.LocalJobRunner:
17/10/20 09:56:56 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:56 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:56 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:56:56 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:56:56 INFO mapreduce.Job:  map 92% reduce 0%
17/10/20 09:56:56 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:56 INFO mapred.Task: Task:attempt_local809729497_0001_m_000140_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:56 INFO mapred.LocalJobRunner: map
17/10/20 09:56:56 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000140_0' done.
17/10/20 09:56:56 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00140_0
17/10/20 09:56:56 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0141_0
17/10/20 09:56:56 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:56 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:56 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:402653184+33554432
17/10/20 09:56:56 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:56 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:56 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:56 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:56 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:56 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:56 INFO mapred.LocalJobRunner:
17/10/20 09:56:56 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:56 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:56 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/20 09:56:56 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(994888                                                                                                                         80); length = 1342177/6553600
17/10/20 09:56:57 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:57 INFO mapred.Task: Task:attempt_local809729497_0001_m_000141_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:57 INFO mapred.LocalJobRunner: map
17/10/20 09:56:57 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000141_0' done.
17/10/20 09:56:57 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00141_0
17/10/20 09:56:57 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0142_0
17/10/20 09:56:57 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:57 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:57 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:369098752+33554432
17/10/20 09:56:57 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:57 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:57 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:57 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:57 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:57 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:57 INFO mapred.LocalJobRunner:
17/10/20 09:56:57 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:57 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:57 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:56:57 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:56:58 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:58 INFO mapred.Task: Task:attempt_local809729497_0001_m_000142_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:58 INFO mapred.LocalJobRunner: map
17/10/20 09:56:58 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000142_0' done.
17/10/20 09:56:58 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00142_0
17/10/20 09:56:58 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0143_0
17/10/20 09:56:58 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:58 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:58 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:335544320+33554432
17/10/20 09:56:58 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:58 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:58 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:58 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:58 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:58 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:58 INFO mapreduce.Job:  map 100% reduce 0%
17/10/20 09:56:58 INFO mapred.LocalJobRunner:
17/10/20 09:56:58 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:58 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:58 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:56:58 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:56:59 INFO mapred.MapTask: Finished spill 0
17/10/20 09:56:59 INFO mapred.Task: Task:attempt_local809729497_0001_m_000143_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:56:59 INFO mapred.LocalJobRunner: map
17/10/20 09:56:59 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000143_0' done.
17/10/20 09:56:59 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00143_0
17/10/20 09:56:59 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0144_0
17/10/20 09:56:59 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:56:59 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:56:59 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:301989888+33554432
17/10/20 09:56:59 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:56:59 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:56:59 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:56:59 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:56:59 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:56:59 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:56:59 INFO mapred.LocalJobRunner:
17/10/20 09:56:59 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:56:59 INFO mapred.MapTask: Spilling map output
17/10/20 09:56:59 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/20 09:56:59 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(994888                                                                                                                         80); length = 1342177/6553600
17/10/20 09:56:59 INFO mapreduce.Job:  map 94% reduce 0%
17/10/20 09:57:00 INFO mapred.MapTask: Finished spill 0
17/10/20 09:57:00 INFO mapred.Task: Task:attempt_local809729497_0001_m_000144_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:57:00 INFO mapred.LocalJobRunner: map
17/10/20 09:57:00 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000144_0' done.
17/10/20 09:57:00 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00144_0
17/10/20 09:57:00 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0145_0
17/10/20 09:57:00 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:57:00 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:57:00 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:268435456+33554432
17/10/20 09:57:00 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:57:00 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:57:00 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:57:00 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:57:00 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:57:00 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:57:00 INFO mapred.LocalJobRunner:
17/10/20 09:57:00 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:57:00 INFO mapred.MapTask: Spilling map output
17/10/20 09:57:00 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:57:00 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:57:00 INFO mapreduce.Job:  map 95% reduce 0%
17/10/20 09:57:00 INFO mapred.MapTask: Finished spill 0
17/10/20 09:57:00 INFO mapred.Task: Task:attempt_local809729497_0001_m_000145_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:57:00 INFO mapred.LocalJobRunner: map
17/10/20 09:57:00 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000145_0' done.
17/10/20 09:57:00 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00145_0
17/10/20 09:57:00 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0146_0
17/10/20 09:57:00 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:57:00 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:57:00 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:234881024+33554432
17/10/20 09:57:00 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:57:00 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:57:00 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:57:00 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:57:00 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:57:00 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:57:01 INFO mapred.LocalJobRunner:
17/10/20 09:57:01 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:57:01 INFO mapred.MapTask: Spilling map output
17/10/20 09:57:01 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:57:01 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:57:01 INFO mapred.MapTask: Finished spill 0
17/10/20 09:57:01 INFO mapred.Task: Task:attempt_local809729497_0001_m_000146_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:57:01 INFO mapred.LocalJobRunner: map
17/10/20 09:57:01 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000146_0' done.
17/10/20 09:57:01 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00146_0
17/10/20 09:57:01 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0147_0
17/10/20 09:57:01 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:57:01 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:57:01 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:201326592+33554432
17/10/20 09:57:01 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:57:01 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:57:01 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:57:01 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:57:01 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:57:01 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:57:02 INFO mapred.LocalJobRunner:
17/10/20 09:57:02 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:57:02 INFO mapred.MapTask: Spilling map output
17/10/20 09:57:02 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/20 09:57:02 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(994888                                                                                                                         80); length = 1342177/6553600
17/10/20 09:57:02 INFO mapreduce.Job:  map 96% reduce 0%
17/10/20 09:57:02 INFO mapred.MapTask: Finished spill 0
17/10/20 09:57:02 INFO mapred.Task: Task:attempt_local809729497_0001_m_000147_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:57:02 INFO mapred.LocalJobRunner: map
17/10/20 09:57:02 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000147_0' done.
17/10/20 09:57:02 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00147_0
17/10/20 09:57:02 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0148_0
17/10/20 09:57:02 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:57:02 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:57:02 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:167772160+33554432
17/10/20 09:57:02 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:57:02 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:57:02 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:57:02 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:57:02 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:57:02 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:57:02 INFO mapred.LocalJobRunner:
17/10/20 09:57:02 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:57:02 INFO mapred.MapTask: Spilling map output
17/10/20 09:57:02 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:57:02 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:57:03 INFO mapred.MapTask: Finished spill 0
17/10/20 09:57:03 INFO mapred.Task: Task:attempt_local809729497_0001_m_000148_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:57:03 INFO mapred.LocalJobRunner: map
17/10/20 09:57:03 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000148_0' done.
17/10/20 09:57:03 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00148_0
17/10/20 09:57:03 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0149_0
17/10/20 09:57:03 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:57:03 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:57:03 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:134217728+33554432
17/10/20 09:57:03 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:57:03 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:57:03 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:57:03 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:57:03 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:57:03 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:57:03 INFO mapreduce.Job:  map 100% reduce 0%
17/10/20 09:57:03 INFO mapred.LocalJobRunner:
17/10/20 09:57:03 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:57:03 INFO mapred.MapTask: Spilling map output
17/10/20 09:57:03 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:57:03 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:57:04 INFO mapred.MapTask: Finished spill 0
17/10/20 09:57:04 INFO mapred.Task: Task:attempt_local809729497_0001_m_000149_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:57:04 INFO mapred.LocalJobRunner: map
17/10/20 09:57:04 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000149_0' done.
17/10/20 09:57:04 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00149_0
17/10/20 09:57:04 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0150_0
17/10/20 09:57:04 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:57:04 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:57:04 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:100663296+33554432
17/10/20 09:57:04 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:57:04 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:57:04 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:57:04 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:57:04 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:57:04 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:57:04 INFO mapred.LocalJobRunner:
17/10/20 09:57:04 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:57:04 INFO mapred.MapTask: Spilling map output
17/10/20 09:57:04 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/20 09:57:04 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(994888                                                                                                                         80); length = 1342177/6553600
17/10/20 09:57:04 INFO mapreduce.Job:  map 98% reduce 0%
17/10/20 09:57:05 INFO mapred.MapTask: Finished spill 0
17/10/20 09:57:05 INFO mapred.Task: Task:attempt_local809729497_0001_m_000150_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:57:05 INFO mapred.LocalJobRunner: map
17/10/20 09:57:05 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000150_0' done.
17/10/20 09:57:05 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00150_0
17/10/20 09:57:05 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0151_0
17/10/20 09:57:05 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:57:05 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:57:05 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:67108864+33554432
17/10/20 09:57:05 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:57:05 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:57:05 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:57:05 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:57:05 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:57:05 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:57:05 INFO mapred.LocalJobRunner:
17/10/20 09:57:05 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:57:05 INFO mapred.MapTask: Spilling map output
17/10/20 09:57:05 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/20 09:57:05 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(994888                                                                                                                         96); length = 1342173/6553600
17/10/20 09:57:05 INFO mapreduce.Job:  map 99% reduce 0%
17/10/20 09:57:06 INFO mapred.MapTask: Finished spill 0
17/10/20 09:57:06 INFO mapred.Task: Task:attempt_local809729497_0001_m_000151_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:57:06 INFO mapred.LocalJobRunner: map
17/10/20 09:57:06 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000151_0' done.
17/10/20 09:57:06 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00151_0
17/10/20 09:57:06 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_m_00                                                                                                                         0152_0
17/10/20 09:57:06 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:57:06 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:57:06 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_ernest/ouput/tg                                                                                                                         en512m/part-m-00000:5100273664+19726336
17/10/20 09:57:06 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 09:57:06 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 09:57:06 INFO mapred.MapTask: soft limit at 83886080
17/10/20 09:57:06 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 09:57:06 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 09:57:06 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.                                                                                                                         MapTask$MapOutputBuffer
17/10/20 09:57:06 INFO mapred.LocalJobRunner:
17/10/20 09:57:06 INFO mapred.MapTask: Starting flush of map output
17/10/20 09:57:06 INFO mapred.MapTask: Spilling map output
17/10/20 09:57:06 INFO mapred.MapTask: bufstart = 0; bufend = 20120826; bufvoid = 104857600
17/10/20 09:57:06 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 25425348(101701                                                                                                                         392); length = 789049/6553600
17/10/20 09:57:06 INFO mapred.MapTask: Finished spill 0
17/10/20 09:57:06 INFO mapred.Task: Task:attempt_local809729497_0001_m_000152_0 is done. And                                                                                                                          is in the process of committing
17/10/20 09:57:06 INFO mapred.LocalJobRunner: map
17/10/20 09:57:06 INFO mapred.Task: Task 'attempt_local809729497_0001_m_000152_0' done.
17/10/20 09:57:06 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_m_0                                                                                                                         00152_0
17/10/20 09:57:06 INFO mapred.LocalJobRunner: map task executor complete.
17/10/20 09:57:06 INFO mapred.LocalJobRunner: Waiting for reduce tasks
17/10/20 09:57:06 INFO mapred.LocalJobRunner: Starting task: attempt_local809729497_0001_r_00                                                                                                                         0000_0
17/10/20 09:57:06 INFO output.FileOutputCommitter: File Output Committer Algorithm version is                                                                                                                          1
17/10/20 09:57:06 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 09:57:06 INFO mapred.ReduceTask: Using ShuffleConsumerPlugin: org.apache.hadoop.mapr                                                                                                                         educe.task.reduce.Shuffle@7caba3f3
17/10/20 09:57:06 INFO reduce.MergeManagerImpl: MergerManager: memoryLimit=652528832, maxSing                                                                                                                         leShuffleLimit=163132208, mergeThreshold=430669056, ioSortFactor=10, memToMemMergeOutputsThre                                                                                                                         shold=10
17/10/20 09:57:06 INFO reduce.EventFetcher: attempt_local809729497_0001_r_000000_0 Thread sta                                                                                                                         rted: EventFetcher for fetching Map Completion Events
17/10/20 09:57:06 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map att                                                                                                                         empt_local809729497_0001_m_000099_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:06 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for atte                                                                                                                         mpt_local809729497_0001_m_000099_0
17/10/20 09:57:06 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 3489                                                                                                                         6578, inMemoryMapOutputs.size() -> 1, commitMemory -> 0, usedMemory ->34896578
17/10/20 09:57:06 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map att                                                                                                                         empt_local809729497_0001_m_000150_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/20 09:57:06 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for atte                                                                                                                         mpt_local809729497_0001_m_000150_0
17/10/20 09:57:06 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 3489                                                                                                                         6682, inMemoryMapOutputs.size() -> 2, commitMemory -> 34896578, usedMemory ->69793260
17/10/20 09:57:06 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map att                                                                                                                         empt_local809729497_0001_m_000048_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:06 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for atte                                                                                                                         mpt_local809729497_0001_m_000048_0
17/10/20 09:57:06 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 3489                                                                                                                         6578, inMemoryMapOutputs.size() -> 3, commitMemory -> 69793260, usedMemory ->104689838
17/10/20 09:57:06 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map att                                                                                                                         empt_local809729497_0001_m_000151_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:06 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for atte                                                                                                                         mpt_local809729497_0001_m_000151_0
17/10/20 09:57:06 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 3489                                                                                                                         6578, inMemoryMapOutputs.size() -> 4, commitMemory -> 104689838, usedMemory ->139586416
17/10/20 09:57:06 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map att                                                                                                                         empt_local809729497_0001_m_000049_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:06 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for atte                                                                                                                         mpt_local809729497_0001_m_000049_0
17/10/20 09:57:06 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 3489                                                                                                                         6578, inMemoryMapOutputs.size() -> 5, commitMemory -> 139586416, usedMemory ->174482994
17/10/20 09:57:06 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map att                                                                                                                         empt_local809729497_0001_m_000100_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/20 09:57:06 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for atte                                                                                                                         mpt_local809729497_0001_m_000100_0
17/10/20 09:57:06 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 3489                                                                                                                         6682, inMemoryMapOutputs.size() -> 6, commitMemory -> 174482994, usedMemory ->209379676
17/10/20 09:57:07 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map att                                                                                                                         empt_local809729497_0001_m_000101_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:07 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for atte                                                                                                                         mpt_local809729497_0001_m_000101_0
17/10/20 09:57:07 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 3489                                                                                                                         6578, inMemoryMapOutputs.size() -> 7, commitMemory -> 209379676, usedMemory ->244276254
17/10/20 09:57:07 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map att                                                                                                                         empt_local809729497_0001_m_000152_0 decomp: 20515354 len: 20515358 to MEMORY
17/10/20 09:57:07 INFO reduce.InMemoryMapOutput: Read 20515354 bytes from map-output for atte                                                                                                                         mpt_local809729497_0001_m_000152_0
17/10/20 09:57:07 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 2051                                                                                                                         5354, inMemoryMapOutputs.size() -> 8, commitMemory -> 244276254, usedMemory ->264791608
17/10/20 09:57:07 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map att                                                                                                                         empt_local809729497_0001_m_000050_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/20 09:57:07 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for atte                                                                                                                         mpt_local809729497_0001_m_000050_0
17/10/20 09:57:07 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 3489                                                                                                                         6682, inMemoryMapOutputs.size() -> 9, commitMemory -> 264791608, usedMemory ->299688290
17/10/20 09:57:07 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map att                                                                                                                         empt_local809729497_0001_m_000044_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/20 09:57:07 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for atte                                                                                                                         mpt_local809729497_0001_m_000044_0
17/10/20 09:57:07 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 3489                                                                                                                         6682, inMemoryMapOutputs.size() -> 10, commitMemory -> 299688290, usedMemory ->334584972
17/10/20 09:57:07 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map att                                                                                                                         empt_local809729497_0001_m_000147_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/20 09:57:07 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for atte                                                                                                                         mpt_local809729497_0001_m_000147_0
17/10/20 09:57:07 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 3489                                                                                                                         6682, inMemoryMapOutputs.size() -> 11, commitMemory -> 334584972, usedMemory ->369481654
17/10/20 09:57:07 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map att                                                                                                                         empt_local809729497_0001_m_000045_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:07 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for atte                                                                                                                         mpt_local809729497_0001_m_000045_0
17/10/20 09:57:07 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 3489                                                                                                                         6578, inMemoryMapOutputs.size() -> 12, commitMemory -> 369481654, usedMemory ->404378232
17/10/20 09:57:07 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map att                                                                                                                         empt_local809729497_0001_m_000096_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:07 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for atte                                                                                                                         mpt_local809729497_0001_m_000096_0
17/10/20 09:57:07 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 3489                                                                                                                         6578, inMemoryMapOutputs.size() -> 13, commitMemory -> 404378232, usedMemory ->439274810
17/10/20 09:57:07 INFO reduce.MergeManagerImpl: Starting inMemoryMerger's merge since commitM                                                                                                                         emory=439274810 > mergeThreshold=430669056. Current usedMemory=439274810
17/10/20 09:57:07 INFO reduce.MergeThread: InMemoryMerger - Thread to merge in-memory shuffle                                                                                                                         d map-outputs: Starting merge with 13 segments, while ignoring 0 segments
17/10/20 09:57:07 INFO reduce.MergeManagerImpl: Initiating in-memory merge with 13 segments..                                                                                                                         .
17/10/20 09:57:07 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map att                                                                                                                         empt_local809729497_0001_m_000097_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/20 09:57:07 INFO mapred.Merger: Merging 13 sorted segments
17/10/20 09:57:07 INFO mapred.Merger: Down to the last merge-pass, with 13 segments left of t                                                                                                                         otal size: 439274641 bytes
17/10/20 09:57:07 INFO mapreduce.Job:  map 100% reduce 0%
17/10/20 09:57:07 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for atte                                                                                                                         mpt_local809729497_0001_m_000097_0
17/10/20 09:57:07 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 3489                                                                                                                         6682, inMemoryMapOutputs.size() -> 1, commitMemory -> 0, usedMemory ->474171492
17/10/20 09:57:07 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map att                                                                                                                         empt_local809729497_0001_m_000148_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:07 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for atte                                                                                                                         mpt_local809729497_0001_m_000148_0
17/10/20 09:57:07 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 3489                                                                                                                         6578, inMemoryMapOutputs.size() -> 2, commitMemory -> 34896682, usedMemory ->509068070
17/10/20 09:57:07 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map att                                                                                                                         empt_local809729497_0001_m_000046_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:07 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for atte                                                                                                                         mpt_local809729497_0001_m_000046_0
17/10/20 09:57:07 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 3489                                                                                                                         6578, inMemoryMapOutputs.size() -> 3, commitMemory -> 69793260, usedMemory ->543964648
17/10/20 09:57:07 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map att                                                                                                                         empt_local809729497_0001_m_000149_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:07 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for atte                                                                                                                         mpt_local809729497_0001_m_000149_0
17/10/20 09:57:07 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 3489                                                                                                                         6578, inMemoryMapOutputs.size() -> 4, commitMemory -> 104689838, usedMemory ->578861226
17/10/20 09:57:07 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map att                                                                                                                         empt_local809729497_0001_m_000047_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/20 09:57:07 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for atte                                                                                                                         mpt_local809729497_0001_m_000047_0
17/10/20 09:57:07 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 3489                                                                                                                         6682, inMemoryMapOutputs.size() -> 5, commitMemory -> 139586416, usedMemory ->613757908
17/10/20 09:57:07 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map att                                                                                                                         empt_local809729497_0001_m_000098_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:08 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for atte                                                                                                                         mpt_local809729497_0001_m_000098_0
17/10/20 09:57:08 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 3489                                                                                                                         6578, inMemoryMapOutputs.size() -> 6, commitMemory -> 174483098, usedMemory ->648654486
17/10/20 09:57:08 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map att                                                                                                                         empt_local809729497_0001_m_000041_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/20 09:57:08 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for atte                                                                                                                         mpt_local809729497_0001_m_000041_0
17/10/20 09:57:08 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 3489                                                                                                                         6682, inMemoryMapOutputs.size() -> 7, commitMemory -> 209379676, usedMemory ->683551168
17/10/20 09:57:08 INFO reduce.LocalFetcher: fetcher#1 - MergeManager returned Status.WAIT ...
17/10/20 09:57:10 INFO reduce.MergeManagerImpl: attempt_local809729497_0001_r_000000_0 Merge of the 13 files in-memory complete. Local file is /tmp/hadoop-ernest/mapred/local/localRunner/ernest/jobcache/job_local809729497_0001/attempt_local809729497_0001_r_000000_0/output/map_152.out.merged of size 439274790
17/10/20 09:57:10 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000092_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:10 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000092_0
17/10/20 09:57:10 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 8, commitMemory -> 244276358, usedMemory ->279172936
17/10/20 09:57:10 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000093_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:10 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000093_0
17/10/20 09:57:10 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 9, commitMemory -> 279172936, usedMemory ->314069514
17/10/20 09:57:10 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000144_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/20 09:57:10 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local809729497_0001_m_000144_0
17/10/20 09:57:10 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 10, commitMemory -> 314069514, usedMemory ->348966196
17/10/20 09:57:10 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000042_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:10 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000042_0
17/10/20 09:57:10 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 11, commitMemory -> 348966196, usedMemory ->383862774
17/10/20 09:57:10 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000145_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:11 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000145_0
17/10/20 09:57:11 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 12, commitMemory -> 383862774, usedMemory ->418759352
17/10/20 09:57:11 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000043_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:11 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000043_0
17/10/20 09:57:11 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 13, commitMemory -> 418759352, usedMemory ->453655930
17/10/20 09:57:11 INFO reduce.MergeManagerImpl: Starting inMemoryMerger's merge since commitMemory=453655930 > mergeThreshold=430669056. Current usedMemory=453655930
17/10/20 09:57:11 INFO reduce.MergeThread: InMemoryMerger - Thread to merge in-memory shuffled map-outputs: Starting merge with 13 segments, while ignoring 0 segments
17/10/20 09:57:11 INFO reduce.MergeManagerImpl: Initiating in-memory merge with 13 segments...
17/10/20 09:57:11 INFO mapred.Merger: Merging 13 sorted segments
17/10/20 09:57:11 INFO mapred.Merger: Down to the last merge-pass, with 13 segments left of total size: 453655761 bytes
17/10/20 09:57:11 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000094_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/20 09:57:11 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local809729497_0001_m_000094_0
17/10/20 09:57:11 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 1, commitMemory -> 0, usedMemory ->488552612
17/10/20 09:57:11 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000095_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:11 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000095_0
17/10/20 09:57:11 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 2, commitMemory -> 34896682, usedMemory ->523449190
17/10/20 09:57:11 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000146_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:11 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000146_0
17/10/20 09:57:11 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 3, commitMemory -> 69793260, usedMemory ->558345768
17/10/20 09:57:11 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000089_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:11 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000089_0
17/10/20 09:57:11 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 4, commitMemory -> 104689838, usedMemory ->593242346
17/10/20 09:57:11 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000140_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:11 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000140_0
17/10/20 09:57:11 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 5, commitMemory -> 139586416, usedMemory ->628138924
17/10/20 09:57:11 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000038_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/20 09:57:11 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local809729497_0001_m_000038_0
17/10/20 09:57:11 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 6, commitMemory -> 174482994, usedMemory ->663035606
17/10/20 09:57:11 INFO reduce.LocalFetcher: fetcher#1 - MergeManager returned Status.WAIT ...
17/10/20 09:57:12 INFO mapred.LocalJobRunner: reduce > copy task(attempt_local809729497_0001_m_000038_0 succeeded at 33280.07 MB/s) Aggregated copy rate(32 of 153 at 1051245.25 MB/s)
17/10/20 09:57:13 INFO mapreduce.Job:  map 100% reduce 7%
17/10/20 09:57:14 INFO reduce.MergeManagerImpl: attempt_local809729497_0001_r_000000_0 Merge of the 13 files in-memory complete. Local file is /tmp/hadoop-ernest/mapred/local/localRunner/ernest/jobcache/job_local809729497_0001/attempt_local809729497_0001_r_000000_0/output/map_148.out.merged of size 453655910
17/10/20 09:57:14 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000141_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/20 09:57:14 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local809729497_0001_m_000141_0
17/10/20 09:57:14 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 7, commitMemory -> 209379676, usedMemory ->244276358
17/10/20 09:57:14 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000039_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:14 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000039_0
17/10/20 09:57:14 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 8, commitMemory -> 244276358, usedMemory ->279172936
17/10/20 09:57:14 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000090_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:14 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000090_0
17/10/20 09:57:14 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 9, commitMemory -> 279172936, usedMemory ->314069514
17/10/20 09:57:14 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000091_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/20 09:57:14 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local809729497_0001_m_000091_0
17/10/20 09:57:14 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 10, commitMemory -> 314069514, usedMemory ->348966196
17/10/20 09:57:14 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000142_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:14 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000142_0
17/10/20 09:57:14 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 11, commitMemory -> 348966196, usedMemory ->383862774
17/10/20 09:57:14 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000040_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:14 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000040_0
17/10/20 09:57:14 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 12, commitMemory -> 383862774, usedMemory ->418759352
17/10/20 09:57:14 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000143_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:14 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000143_0
17/10/20 09:57:14 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 13, commitMemory -> 418759352, usedMemory ->453655930
17/10/20 09:57:14 INFO reduce.MergeManagerImpl: Starting inMemoryMerger's merge since commitMemory=453655930 > mergeThreshold=430669056. Current usedMemory=453655930
17/10/20 09:57:14 INFO reduce.MergeThread: InMemoryMerger - Thread to merge in-memory shuffled map-outputs: Starting merge with 13 segments, while ignoring 0 segments
17/10/20 09:57:14 INFO reduce.MergeManagerImpl: Initiating in-memory merge with 13 segments...
17/10/20 09:57:14 INFO mapred.Merger: Merging 13 sorted segments
17/10/20 09:57:14 INFO mapred.Merger: Down to the last merge-pass, with 13 segments left of total size: 453655761 bytes
17/10/20 09:57:15 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000009_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:15 INFO mapred.LocalJobRunner: reduce > copy task(attempt_local809729497_0001_m_000143_0 succeeded at 33279.98 MB/s) Aggregated copy rate(39 of 153 at 1284205.38 MB/s)
17/10/20 09:57:15 INFO mapreduce.Job:  map 100% reduce 8%
17/10/20 09:57:18 INFO reduce.MergeManagerImpl: attempt_local809729497_0001_r_000000_0 Merge of the 13 files in-memory complete. Local file is /tmp/hadoop-ernest/mapred/local/localRunner/ernest/jobcache/job_local809729497_0001/attempt_local809729497_0001_r_000000_0/output/map_95.out.merged of size 453655910
17/10/20 09:57:18 INFO mapred.LocalJobRunner: reduce > copy task(attempt_local809729497_0001_m_000143_0 succeeded at 33279.98 MB/s) Aggregated copy rate(39 of 153 at 1284205.38 MB/s)
17/10/20 09:57:21 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000009_0
17/10/20 09:57:21 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 1, commitMemory -> 0, usedMemory ->34896578
17/10/20 09:57:21 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000060_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/20 09:57:21 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local809729497_0001_m_000060_0
17/10/20 09:57:21 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 2, commitMemory -> 34896578, usedMemory ->69793260
17/10/20 09:57:21 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000061_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:21 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000061_0
17/10/20 09:57:21 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 3, commitMemory -> 69793260, usedMemory ->104689838
17/10/20 09:57:21 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000112_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:21 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000112_0
17/10/20 09:57:21 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 4, commitMemory -> 104689838, usedMemory ->139586416
17/10/20 09:57:21 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000010_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/20 09:57:21 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local809729497_0001_m_000010_0
17/10/20 09:57:21 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 5, commitMemory -> 139586416, usedMemory ->174483098
17/10/20 09:57:21 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000113_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/20 09:57:21 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local809729497_0001_m_000113_0
17/10/20 09:57:21 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 6, commitMemory -> 174483098, usedMemory ->209379780
17/10/20 09:57:21 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000011_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:21 INFO mapred.LocalJobRunner: reduce > copy task(attempt_local809729497_0001_m_000113_0 succeeded at 33280.07 MB/s) Aggregated copy rate(45 of 153 at 1483885.38 MB/s)
17/10/20 09:57:21 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000011_0
17/10/20 09:57:21 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 7, commitMemory -> 209379780, usedMemory ->244276358
17/10/20 09:57:21 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000062_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:21 INFO mapreduce.Job:  map 100% reduce 10%
17/10/20 09:57:21 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000062_0
17/10/20 09:57:21 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 8, commitMemory -> 244276358, usedMemory ->279172936
17/10/20 09:57:21 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000063_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/20 09:57:21 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local809729497_0001_m_000063_0
17/10/20 09:57:21 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 9, commitMemory -> 279172936, usedMemory ->314069618
17/10/20 09:57:21 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000114_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:21 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000114_0
17/10/20 09:57:21 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 10, commitMemory -> 314069618, usedMemory ->348966196
17/10/20 09:57:21 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000057_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/20 09:57:21 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local809729497_0001_m_000057_0
17/10/20 09:57:21 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 11, commitMemory -> 348966196, usedMemory ->383862878
17/10/20 09:57:21 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000108_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:21 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000108_0
17/10/20 09:57:21 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 12, commitMemory -> 383862878, usedMemory ->418759456
17/10/20 09:57:21 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000006_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:22 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000006_0
17/10/20 09:57:22 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 13, commitMemory -> 418759456, usedMemory ->453656034
17/10/20 09:57:22 INFO reduce.MergeManagerImpl: Starting inMemoryMerger's merge since commitMemory=453656034 > mergeThreshold=430669056. Current usedMemory=453656034
17/10/20 09:57:22 INFO reduce.MergeThread: InMemoryMerger - Thread to merge in-memory shuffled map-outputs: Starting merge with 13 segments, while ignoring 0 segments
17/10/20 09:57:22 INFO reduce.MergeManagerImpl: Initiating in-memory merge with 13 segments...
17/10/20 09:57:22 INFO mapred.Merger: Merging 13 sorted segments
17/10/20 09:57:22 INFO mapred.Merger: Down to the last merge-pass, with 13 segments left of total size: 453655865 bytes
17/10/20 09:57:22 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000109_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:22 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000109_0
17/10/20 09:57:22 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 1, commitMemory -> 0, usedMemory ->488552612
17/10/20 09:57:22 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000007_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/20 09:57:22 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local809729497_0001_m_000007_0
17/10/20 09:57:22 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 2, commitMemory -> 34896578, usedMemory ->523449294
17/10/20 09:57:22 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000058_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:22 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000058_0
17/10/20 09:57:22 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 3, commitMemory -> 69793260, usedMemory ->558345872
17/10/20 09:57:22 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000059_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:22 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000059_0
17/10/20 09:57:22 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 4, commitMemory -> 104689838, usedMemory ->593242450
17/10/20 09:57:22 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000110_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/20 09:57:22 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local809729497_0001_m_000110_0
17/10/20 09:57:22 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 5, commitMemory -> 139586416, usedMemory ->628139132
17/10/20 09:57:22 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000008_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:22 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000008_0
17/10/20 09:57:22 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 6, commitMemory -> 174483098, usedMemory ->663035710
17/10/20 09:57:22 INFO reduce.LocalFetcher: fetcher#1 - MergeManager returned Status.WAIT ...
17/10/20 09:57:24 INFO mapred.LocalJobRunner: reduce > copy task(attempt_local809729497_0001_m_000008_0 succeeded at 33279.98 MB/s) Aggregated copy rate(58 of 153 at 1916525.50 MB/s)
17/10/20 09:57:24 INFO mapreduce.Job:  map 100% reduce 13%
17/10/20 09:57:25 INFO reduce.MergeManagerImpl: attempt_local809729497_0001_r_000000_0 Merge of the 13 files in-memory complete. Local file is /tmp/hadoop-ernest/mapred/local/localRunner/ernest/jobcache/job_local809729497_0001/attempt_local809729497_0001_r_000000_0/output/map_9.out.merged of size 453656014
17/10/20 09:57:25 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000111_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:25 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000111_0
17/10/20 09:57:25 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 7, commitMemory -> 209379676, usedMemory ->244276254
17/10/20 09:57:25 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000105_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:25 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000105_0
17/10/20 09:57:25 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 8, commitMemory -> 244276254, usedMemory ->279172832
17/10/20 09:57:26 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000003_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/20 09:57:27 INFO mapred.LocalJobRunner: reduce > copy task(attempt_local809729497_0001_m_000105_0 succeeded at 33279.98 MB/s) Aggregated copy rate(60 of 153 at 1983085.50 MB/s)
17/10/20 09:57:30 INFO mapred.LocalJobRunner: reduce > copy task(attempt_local809729497_0001_m_000105_0 succeeded at 33279.98 MB/s) Aggregated copy rate(60 of 153 at 1983085.50 MB/s)
17/10/20 09:57:32 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local809729497_0001_m_000003_0
17/10/20 09:57:32 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 9, commitMemory -> 279172832, usedMemory ->314069514
17/10/20 09:57:32 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000054_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:32 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000054_0
17/10/20 09:57:32 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 10, commitMemory -> 314069514, usedMemory ->348966092
17/10/20 09:57:32 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000055_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:32 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000055_0
17/10/20 09:57:32 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 11, commitMemory -> 348966092, usedMemory ->383862670
17/10/20 09:57:32 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000106_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:32 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000106_0
17/10/20 09:57:32 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 12, commitMemory -> 383862670, usedMemory ->418759248
17/10/20 09:57:33 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000004_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:33 INFO mapred.LocalJobRunner: reduce > copy task(attempt_local809729497_0001_m_000106_0 succeeded at 33279.98 MB/s) Aggregated copy rate(64 of 153 at 2116205.25 MB/s)
17/10/20 09:57:33 INFO mapreduce.Job:  map 100% reduce 14%
17/10/20 09:57:35 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000004_0
17/10/20 09:57:35 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 13, commitMemory -> 418759248, usedMemory ->453655826
17/10/20 09:57:35 INFO reduce.MergeManagerImpl: Starting inMemoryMerger's merge since commitMemory=453655826 > mergeThreshold=430669056. Current usedMemory=453655826
17/10/20 09:57:35 INFO reduce.MergeThread: InMemoryMerger - Thread to merge in-memory shuffled map-outputs: Starting merge with 13 segments, while ignoring 0 segments
17/10/20 09:57:35 INFO reduce.MergeManagerImpl: Initiating in-memory merge with 13 segments...
17/10/20 09:57:35 INFO mapred.Merger: Merging 13 sorted segments
17/10/20 09:57:35 INFO mapred.Merger: Down to the last merge-pass, with 13 segments left of total size: 453655657 bytes
17/10/20 09:57:35 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000107_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/20 09:57:35 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local809729497_0001_m_000107_0
17/10/20 09:57:35 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 1, commitMemory -> 0, usedMemory ->488552508
17/10/20 09:57:35 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000005_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:36 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000005_0
17/10/20 09:57:36 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 2, commitMemory -> 34896682, usedMemory ->523449086
17/10/20 09:57:36 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000056_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:36 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000056_0
17/10/20 09:57:36 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 3, commitMemory -> 69793260, usedMemory ->558345664
17/10/20 09:57:36 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000051_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:36 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000051_0
17/10/20 09:57:36 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 4, commitMemory -> 104689838, usedMemory ->593242242
17/10/20 09:57:36 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000102_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:36 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000102_0
17/10/20 09:57:36 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 5, commitMemory -> 139586416, usedMemory ->628138820
17/10/20 09:57:36 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000000_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/20 09:57:36 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local809729497_0001_m_000000_0
17/10/20 09:57:36 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 6, commitMemory -> 174482994, usedMemory ->663035502
17/10/20 09:57:36 INFO reduce.LocalFetcher: fetcher#1 - MergeManager returned Status.WAIT ...
17/10/20 09:57:36 INFO mapred.LocalJobRunner: reduce > copy task(attempt_local809729497_0001_m_000000_0 succeeded at 33280.07 MB/s) Aggregated copy rate(71 of 153 at 2349165.50 MB/s)
17/10/20 09:57:36 INFO mapreduce.Job:  map 100% reduce 15%
17/10/20 09:57:38 INFO reduce.MergeManagerImpl: attempt_local809729497_0001_r_000000_0 Merge of the 13 files in-memory complete. Local file is /tmp/hadoop-ernest/mapred/local/localRunner/ernest/jobcache/job_local809729497_0001/attempt_local809729497_0001_r_000000_0/output/map_109.out.merged of size 453655806
17/10/20 09:57:38 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000103_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/20 09:57:38 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local809729497_0001_m_000103_0
17/10/20 09:57:38 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 7, commitMemory -> 209379676, usedMemory ->244276358
17/10/20 09:57:38 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000001_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:39 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000001_0
17/10/20 09:57:39 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 8, commitMemory -> 244276358, usedMemory ->279172936
17/10/20 09:57:39 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000052_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:39 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000052_0
17/10/20 09:57:39 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 9, commitMemory -> 279172936, usedMemory ->314069514
17/10/20 09:57:39 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000053_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/20 09:57:39 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local809729497_0001_m_000053_0
17/10/20 09:57:39 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 10, commitMemory -> 314069514, usedMemory ->348966196
17/10/20 09:57:39 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000104_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:39 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000104_0
17/10/20 09:57:39 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 11, commitMemory -> 348966196, usedMemory ->383862774
17/10/20 09:57:39 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000002_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:39 INFO mapred.LocalJobRunner: reduce > copy task(attempt_local809729497_0001_m_000104_0 succeeded at 33279.98 MB/s) Aggregated copy rate(76 of 153 at 2515565.50 MB/s)
17/10/20 09:57:39 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000002_0
17/10/20 09:57:39 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 12, commitMemory -> 383862774, usedMemory ->418759352
17/10/20 09:57:39 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000073_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:39 INFO mapreduce.Job:  map 100% reduce 17%
17/10/20 09:57:39 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000073_0
17/10/20 09:57:39 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 13, commitMemory -> 418759352, usedMemory ->453655930
17/10/20 09:57:39 INFO reduce.MergeManagerImpl: Starting inMemoryMerger's merge since commitMemory=453655930 > mergeThreshold=430669056. Current usedMemory=453655930
17/10/20 09:57:39 INFO reduce.MergeThread: InMemoryMerger - Thread to merge in-memory shuffled map-outputs: Starting merge with 13 segments, while ignoring 0 segments
17/10/20 09:57:39 INFO reduce.MergeManagerImpl: Initiating in-memory merge with 13 segments...
17/10/20 09:57:39 INFO mapred.Merger: Merging 13 sorted segments
17/10/20 09:57:39 INFO mapred.Merger: Down to the last merge-pass, with 13 segments left of total size: 453655761 bytes
17/10/20 09:57:39 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000124_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:39 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000124_0
17/10/20 09:57:39 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 1, commitMemory -> 0, usedMemory ->488552508
17/10/20 09:57:39 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000022_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/20 09:57:40 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local809729497_0001_m_000022_0
17/10/20 09:57:40 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 2, commitMemory -> 34896578, usedMemory ->523449190
17/10/20 09:57:40 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000125_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/20 09:57:40 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local809729497_0001_m_000125_0
17/10/20 09:57:40 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 3, commitMemory -> 69793260, usedMemory ->558345872
17/10/20 09:57:40 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000023_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:40 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000023_0
17/10/20 09:57:40 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 4, commitMemory -> 104689942, usedMemory ->593242450
17/10/20 09:57:40 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000074_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:40 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000074_0
17/10/20 09:57:40 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 5, commitMemory -> 139586520, usedMemory ->628139028
17/10/20 09:57:40 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000075_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/20 09:57:40 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local809729497_0001_m_000075_0
17/10/20 09:57:40 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 6, commitMemory -> 174483098, usedMemory ->663035710
17/10/20 09:57:40 INFO reduce.LocalFetcher: fetcher#1 - MergeManager returned Status.WAIT ...
17/10/20 09:57:42 INFO mapred.LocalJobRunner: reduce > copy task(attempt_local809729497_0001_m_000075_0 succeeded at 33280.07 MB/s) Aggregated copy rate(84 of 153 at 2781805.75 MB/s)
17/10/20 09:57:42 INFO mapreduce.Job:  map 100% reduce 18%
17/10/20 09:57:43 INFO reduce.MergeManagerImpl: attempt_local809729497_0001_r_000000_0 Merge of the 13 files in-memory complete. Local file is /tmp/hadoop-ernest/mapred/local/localRunner/ernest/jobcache/job_local809729497_0001/attempt_local809729497_0001_r_000000_0/output/map_5.out.merged of size 453655910
17/10/20 09:57:43 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000126_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:43 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000126_0
17/10/20 09:57:43 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 7, commitMemory -> 209379780, usedMemory ->244276358
17/10/20 09:57:43 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000024_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:43 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000024_0
17/10/20 09:57:43 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 8, commitMemory -> 244276358, usedMemory ->279172936
17/10/20 09:57:43 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000127_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:43 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000127_0
17/10/20 09:57:43 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 9, commitMemory -> 279172936, usedMemory ->314069514
17/10/20 09:57:43 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000121_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:43 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000121_0
17/10/20 09:57:43 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 10, commitMemory -> 314069514, usedMemory ->348966092
17/10/20 09:57:43 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000019_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/20 09:57:43 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local809729497_0001_m_000019_0
17/10/20 09:57:43 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 11, commitMemory -> 348966092, usedMemory ->383862774
17/10/20 09:57:43 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000070_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:43 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000070_0
17/10/20 09:57:43 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 12, commitMemory -> 383862774, usedMemory ->418759352
17/10/20 09:57:44 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000071_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:44 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000071_0
17/10/20 09:57:44 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 13, commitMemory -> 418759352, usedMemory ->453655930
17/10/20 09:57:44 INFO reduce.MergeManagerImpl: Starting inMemoryMerger's merge since commitMemory=453655930 > mergeThreshold=430669056. Current usedMemory=453655930
17/10/20 09:57:44 INFO reduce.MergeThread: InMemoryMerger - Thread to merge in-memory shuffled map-outputs: Starting merge with 13 segments, while ignoring 0 segments
17/10/20 09:57:44 INFO reduce.MergeManagerImpl: Initiating in-memory merge with 13 segments...
17/10/20 09:57:44 INFO mapred.Merger: Merging 13 sorted segments
17/10/20 09:57:44 INFO mapred.Merger: Down to the last merge-pass, with 13 segments left of total size: 453655761 bytes
17/10/20 09:57:44 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000122_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/20 09:57:44 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local809729497_0001_m_000122_0
17/10/20 09:57:44 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 1, commitMemory -> 0, usedMemory ->488552612
17/10/20 09:57:44 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000020_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:44 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000020_0
17/10/20 09:57:44 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 2, commitMemory -> 34896682, usedMemory ->523449190
17/10/20 09:57:44 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000123_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:44 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000123_0
17/10/20 09:57:44 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 3, commitMemory -> 69793260, usedMemory ->558345768
17/10/20 09:57:44 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000021_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:45 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000021_0
17/10/20 09:57:45 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 4, commitMemory -> 104689838, usedMemory ->593242346
17/10/20 09:57:45 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000072_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/20 09:57:45 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local809729497_0001_m_000072_0
17/10/20 09:57:45 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 5, commitMemory -> 139586416, usedMemory ->628139028
17/10/20 09:57:45 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000067_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:45 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000067_0
17/10/20 09:57:45 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 6, commitMemory -> 174483098, usedMemory ->663035606
17/10/20 09:57:45 INFO reduce.LocalFetcher: fetcher#1 - MergeManager returned Status.WAIT ...
17/10/20 09:57:45 INFO mapred.LocalJobRunner: reduce > copy task(attempt_local809729497_0001_m_000067_0 succeeded at 33279.98 MB/s) Aggregated copy rate(97 of 153 at 3214445.50 MB/s)
17/10/20 09:57:45 INFO mapreduce.Job:  map 100% reduce 21%
17/10/20 09:57:47 INFO reduce.MergeManagerImpl: attempt_local809729497_0001_r_000000_0 Merge of the 13 files in-memory complete. Local file is /tmp/hadoop-ernest/mapred/local/localRunner/ernest/jobcache/job_local809729497_0001/attempt_local809729497_0001_r_000000_0/output/map_124.out.merged of size 453655910
17/10/20 09:57:47 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000118_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:48 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000118_0
17/10/20 09:57:48 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 7, commitMemory -> 209379676, usedMemory ->244276254
17/10/20 09:57:48 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000016_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/20 09:57:48 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local809729497_0001_m_000016_0
17/10/20 09:57:48 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 8, commitMemory -> 244276254, usedMemory ->279172936
17/10/20 09:57:48 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000119_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/20 09:57:48 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local809729497_0001_m_000119_0
17/10/20 09:57:48 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 9, commitMemory -> 279172936, usedMemory ->314069618
17/10/20 09:57:48 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000017_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:48 INFO mapred.LocalJobRunner: reduce > copy task(attempt_local809729497_0001_m_000119_0 succeeded at 33280.07 MB/s) Aggregated copy rate(100 of 153 at 3314285.75 MB/s)
17/10/20 09:57:48 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000017_0
17/10/20 09:57:48 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 10, commitMemory -> 314069618, usedMemory ->348966196
17/10/20 09:57:48 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000068_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:48 INFO mapreduce.Job:  map 100% reduce 22%
17/10/20 09:57:48 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000068_0
17/10/20 09:57:48 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 11, commitMemory -> 348966196, usedMemory ->383862774
17/10/20 09:57:48 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000069_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/20 09:57:49 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local809729497_0001_m_000069_0
17/10/20 09:57:49 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 12, commitMemory -> 383862774, usedMemory ->418759456
17/10/20 09:57:49 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000120_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:49 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000120_0
17/10/20 09:57:49 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 13, commitMemory -> 418759456, usedMemory ->453656034
17/10/20 09:57:49 INFO reduce.MergeManagerImpl: Starting inMemoryMerger's merge since commitMemory=453656034 > mergeThreshold=430669056. Current usedMemory=453656034
17/10/20 09:57:49 INFO reduce.MergeThread: InMemoryMerger - Thread to merge in-memory shuffled map-outputs: Starting merge with 13 segments, while ignoring 0 segments
17/10/20 09:57:49 INFO reduce.MergeManagerImpl: Initiating in-memory merge with 13 segments...
17/10/20 09:57:49 INFO mapred.Merger: Merging 13 sorted segments
17/10/20 09:57:49 INFO mapred.Merger: Down to the last merge-pass, with 13 segments left of total size: 453655865 bytes
17/10/20 09:57:49 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000018_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:49 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000018_0
17/10/20 09:57:49 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 1, commitMemory -> 0, usedMemory ->488552612
17/10/20 09:57:49 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000012_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:49 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000012_0
17/10/20 09:57:49 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 2, commitMemory -> 34896578, usedMemory ->523449190
17/10/20 09:57:49 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000115_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:50 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000115_0
17/10/20 09:57:50 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 3, commitMemory -> 69793156, usedMemory ->558345768
17/10/20 09:57:50 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000013_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/20 09:57:50 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local809729497_0001_m_000013_0
17/10/20 09:57:50 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 4, commitMemory -> 104689734, usedMemory ->593242450
17/10/20 09:57:50 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000064_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:51 INFO mapred.LocalJobRunner: reduce > copy task(attempt_local809729497_0001_m_000013_0 succeeded at 33280.07 MB/s) Aggregated copy rate(108 of 153 at 3580525.75 MB/s)
17/10/20 09:57:51 INFO mapreduce.Job:  map 100% reduce 24%
17/10/20 09:57:52 INFO reduce.MergeManagerImpl: attempt_local809729497_0001_r_000000_0 Merge of the 13 files in-memory complete. Local file is /tmp/hadoop-ernest/mapred/local/localRunner/ernest/jobcache/job_local809729497_0001/attempt_local809729497_0001_r_000000_0/output/map_20.out.merged of size 453656014
17/10/20 09:57:53 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000064_0
17/10/20 09:57:53 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 5, commitMemory -> 139586416, usedMemory ->174482994
17/10/20 09:57:53 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000065_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:57:54 INFO mapred.LocalJobRunner: reduce > copy task(attempt_local809729497_0001_m_000064_0 succeeded at 33279.98 MB/s) Aggregated copy rate(109 of 153 at 3613805.75 MB/s)
17/10/20 09:57:57 INFO mapred.LocalJobRunner: reduce > copy task(attempt_local809729497_0001_m_000064_0 succeeded at 33279.98 MB/s) Aggregated copy rate(109 of 153 at 3613805.75 MB/s)
17/10/20 09:57:59 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000065_0
17/10/20 09:57:59 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 6, commitMemory -> 174482994, usedMemory ->209379572
17/10/20 09:57:59 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000116_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/20 09:58:00 INFO mapred.LocalJobRunner: reduce > copy task(attempt_local809729497_0001_m_000065_0 succeeded at 33279.98 MB/s) Aggregated copy rate(110 of 153 at 3647085.75 MB/s)
17/10/20 09:58:03 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local809729497_0001_m_000116_0
17/10/20 09:58:03 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 7, commitMemory -> 209379572, usedMemory ->244276254
17/10/20 09:58:03 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000014_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:58:03 INFO mapred.LocalJobRunner: reduce > copy task(attempt_local809729497_0001_m_000116_0 succeeded at 33280.07 MB/s) Aggregated copy rate(111 of 153 at 3680365.75 MB/s)
17/10/20 09:58:03 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000014_0
17/10/20 09:58:03 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 8, commitMemory -> 244276254, usedMemory ->279172832
17/10/20 09:58:03 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000117_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:58:03 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000117_0
17/10/20 09:58:03 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 9, commitMemory -> 279172832, usedMemory ->314069410
17/10/20 09:58:03 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000015_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:58:04 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000015_0
17/10/20 09:58:04 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 10, commitMemory -> 314069410, usedMemory ->348965988
17/10/20 09:58:04 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000066_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/20 09:58:04 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local809729497_0001_m_000066_0
17/10/20 09:58:04 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 11, commitMemory -> 348965988, usedMemory ->383862670
17/10/20 09:58:04 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000137_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:58:04 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000137_0
17/10/20 09:58:04 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 12, commitMemory -> 383862670, usedMemory ->418759248
17/10/20 09:58:04 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000035_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/20 09:58:04 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local809729497_0001_m_000035_0
17/10/20 09:58:04 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 13, commitMemory -> 418759248, usedMemory ->453655930
17/10/20 09:58:04 INFO reduce.MergeManagerImpl: Starting inMemoryMerger's merge since commitMemory=453655930 > mergeThreshold=430669056. Current usedMemory=453655930
17/10/20 09:58:04 INFO reduce.MergeThread: InMemoryMerger - Thread to merge in-memory shuffled map-outputs: Starting merge with 13 segments, while ignoring 0 segments
17/10/20 09:58:04 INFO reduce.MergeManagerImpl: Initiating in-memory merge with 13 segments...
17/10/20 09:58:04 INFO mapred.Merger: Merging 13 sorted segments
17/10/20 09:58:04 INFO mapred.Merger: Down to the last merge-pass, with 13 segments left of total size: 453655761 bytes
17/10/20 09:58:04 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000086_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:58:05 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000086_0
17/10/20 09:58:05 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 1, commitMemory -> 0, usedMemory ->488552508
17/10/20 09:58:05 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000087_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:58:05 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000087_0
17/10/20 09:58:05 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 2, commitMemory -> 34896578, usedMemory ->523449086
17/10/20 09:58:05 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000138_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/20 09:58:05 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local809729497_0001_m_000138_0
17/10/20 09:58:05 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 3, commitMemory -> 69793156, usedMemory ->558345768
17/10/20 09:58:05 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000036_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:58:05 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000036_0
17/10/20 09:58:05 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 4, commitMemory -> 104689838, usedMemory ->593242346
17/10/20 09:58:05 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000139_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:58:05 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000139_0
17/10/20 09:58:05 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 5, commitMemory -> 139586416, usedMemory ->628138924
17/10/20 09:58:05 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000037_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:58:06 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000037_0
17/10/20 09:58:06 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 6, commitMemory -> 174482994, usedMemory ->663035502
17/10/20 09:58:06 INFO reduce.LocalFetcher: fetcher#1 - MergeManager returned Status.WAIT ...
17/10/20 09:58:06 INFO mapred.LocalJobRunner: reduce > copy task(attempt_local809729497_0001_m_000037_0 succeeded at 33279.98 MB/s) Aggregated copy rate(123 of 153 at 4079725.50 MB/s)
17/10/20 09:58:06 INFO mapreduce.Job:  map 100% reduce 27%
17/10/20 09:58:07 INFO reduce.MergeManagerImpl: attempt_local809729497_0001_r_000000_0 Merge of the 13 files in-memory complete. Local file is /tmp/hadoop-ernest/mapred/local/localRunner/ernest/jobcache/job_local809729497_0001/attempt_local809729497_0001_r_000000_0/output/map_18.out.merged of size 453655910
17/10/20 09:58:07 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000088_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/20 09:58:08 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local809729497_0001_m_000088_0
17/10/20 09:58:08 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 7, commitMemory -> 209379572, usedMemory ->244276254
17/10/20 09:58:08 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000083_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:58:08 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000083_0
17/10/20 09:58:08 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 8, commitMemory -> 244276254, usedMemory ->279172832
17/10/20 09:58:08 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000134_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:58:08 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000134_0
17/10/20 09:58:08 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 9, commitMemory -> 279172832, usedMemory ->314069410
17/10/20 09:58:08 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000032_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/20 09:58:08 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local809729497_0001_m_000032_0
17/10/20 09:58:08 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 10, commitMemory -> 314069410, usedMemory ->348966092
17/10/20 09:58:08 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000135_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/20 09:58:08 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local809729497_0001_m_000135_0
17/10/20 09:58:08 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 11, commitMemory -> 348966092, usedMemory ->383862774
17/10/20 09:58:08 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000033_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:58:09 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000033_0
17/10/20 09:58:09 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 12, commitMemory -> 383862774, usedMemory ->418759352
17/10/20 09:58:09 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000084_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:58:09 INFO mapred.LocalJobRunner: reduce > copy task(attempt_local809729497_0001_m_000033_0 succeeded at 33279.98 MB/s) Aggregated copy rate(129 of 153 at 4279406.00 MB/s)
17/10/20 09:58:09 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000084_0
17/10/20 09:58:09 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 13, commitMemory -> 418759352, usedMemory ->453655930
17/10/20 09:58:09 INFO reduce.MergeManagerImpl: Starting inMemoryMerger's merge since commitMemory=453655930 > mergeThreshold=430669056. Current usedMemory=453655930
17/10/20 09:58:09 INFO reduce.MergeThread: InMemoryMerger - Thread to merge in-memory shuffled map-outputs: Starting merge with 13 segments, while ignoring 0 segments
17/10/20 09:58:09 INFO reduce.MergeManagerImpl: Initiating in-memory merge with 13 segments...
17/10/20 09:58:09 INFO mapred.Merger: Merging 13 sorted segments
17/10/20 09:58:09 INFO mapred.Merger: Down to the last merge-pass, with 13 segments left of total size: 453655761 bytes
17/10/20 09:58:09 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000085_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/20 09:58:09 INFO mapreduce.Job:  map 100% reduce 28%
17/10/20 09:58:10 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local809729497_0001_m_000085_0
17/10/20 09:58:10 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 1, commitMemory -> 0, usedMemory ->488552612
17/10/20 09:58:10 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000136_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:58:10 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000136_0
17/10/20 09:58:10 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 2, commitMemory -> 34896682, usedMemory ->523449190
17/10/20 09:58:10 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000034_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:58:11 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000034_0
17/10/20 09:58:11 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 3, commitMemory -> 69793260, usedMemory ->558345768
17/10/20 09:58:11 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000028_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/20 09:58:11 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local809729497_0001_m_000028_0
17/10/20 09:58:11 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 4, commitMemory -> 104689838, usedMemory ->593242450
17/10/20 09:58:11 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000131_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:58:12 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000131_0
17/10/20 09:58:12 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 5, commitMemory -> 139586520, usedMemory ->628139028
17/10/20 09:58:12 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000029_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:58:12 INFO mapred.LocalJobRunner: reduce > copy task(attempt_local809729497_0001_m_000131_0 succeeded at 33279.98 MB/s) Aggregated copy rate(135 of 153 at 4479086.00 MB/s)
17/10/20 09:58:12 INFO reduce.MergeManagerImpl: attempt_local809729497_0001_r_000000_0 Merge of the 13 files in-memory complete. Local file is /tmp/hadoop-ernest/mapred/local/localRunner/ernest/jobcache/job_local809729497_0001/attempt_local809729497_0001_r_000000_0/output/map_86.out.merged of size 453655910
17/10/20 09:58:12 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000029_0
17/10/20 09:58:12 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 6, commitMemory -> 174483098, usedMemory ->209379676
17/10/20 09:58:12 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000080_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:58:12 INFO mapreduce.Job:  map 100% reduce 29%
17/10/20 09:58:13 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000080_0
17/10/20 09:58:13 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 7, commitMemory -> 209379676, usedMemory ->244276254
17/10/20 09:58:13 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000081_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:58:13 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000081_0
17/10/20 09:58:13 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 8, commitMemory -> 244276254, usedMemory ->279172832
17/10/20 09:58:13 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000132_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/20 09:58:14 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local809729497_0001_m_000132_0
17/10/20 09:58:14 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 9, commitMemory -> 279172832, usedMemory ->314069514
17/10/20 09:58:14 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000030_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:58:14 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000030_0
17/10/20 09:58:14 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 10, commitMemory -> 314069514, usedMemory ->348966092
17/10/20 09:58:14 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000133_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:58:15 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000133_0
17/10/20 09:58:15 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 11, commitMemory -> 348966092, usedMemory ->383862670
17/10/20 09:58:15 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000031_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:58:15 INFO mapred.LocalJobRunner: reduce > copy task(attempt_local809729497_0001_m_000133_0 succeeded at 33279.98 MB/s) Aggregated copy rate(141 of 153 at 4678765.50 MB/s)
17/10/20 09:58:15 INFO mapreduce.Job:  map 100% reduce 31%
17/10/20 09:58:15 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000031_0
17/10/20 09:58:15 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 12, commitMemory -> 383862670, usedMemory ->418759248
17/10/20 09:58:16 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000082_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/20 09:58:16 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local809729497_0001_m_000082_0
17/10/20 09:58:16 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 13, commitMemory -> 418759248, usedMemory ->453655930
17/10/20 09:58:16 INFO reduce.MergeManagerImpl: Starting inMemoryMerger's merge since commitMemory=453655930 > mergeThreshold=430669056. Current usedMemory=453655930
17/10/20 09:58:16 INFO reduce.MergeThread: InMemoryMerger - Thread to merge in-memory shuffled map-outputs: Starting merge with 13 segments, while ignoring 0 segments
17/10/20 09:58:16 INFO reduce.MergeManagerImpl: Initiating in-memory merge with 13 segments...
17/10/20 09:58:16 INFO mapred.Merger: Merging 13 sorted segments
17/10/20 09:58:16 INFO mapred.Merger: Down to the last merge-pass, with 13 segments left of total size: 453655761 bytes
17/10/20 09:58:16 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000025_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/20 09:58:17 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local809729497_0001_m_000025_0
17/10/20 09:58:17 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 1, commitMemory -> 0, usedMemory ->488552612
17/10/20 09:58:17 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000076_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:58:17 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000076_0
17/10/20 09:58:17 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 2, commitMemory -> 34896682, usedMemory ->523449190
17/10/20 09:58:17 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000077_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:58:18 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000077_0
17/10/20 09:58:18 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 3, commitMemory -> 69793260, usedMemory ->558345768
17/10/20 09:58:18 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000128_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/20 09:58:18 INFO mapred.LocalJobRunner: reduce > copy task(attempt_local809729497_0001_m_000077_0 succeeded at 33279.98 MB/s) Aggregated copy rate(146 of 153 at 4845166.00 MB/s)
17/10/20 09:58:18 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local809729497_0001_m_000128_0
17/10/20 09:58:18 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 4, commitMemory -> 104689838, usedMemory ->593242450
17/10/20 09:58:18 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000026_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:58:18 INFO mapreduce.Job:  map 100% reduce 32%
17/10/20 09:58:19 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000026_0
17/10/20 09:58:19 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 5, commitMemory -> 139586520, usedMemory ->628139028
17/10/20 09:58:19 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000129_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:58:19 INFO reduce.MergeManagerImpl: attempt_local809729497_0001_r_000000_0 Merge of the 13 files in-memory complete. Local file is /tmp/hadoop-ernest/mapred/local/localRunner/ernest/jobcache/job_local809729497_0001/attempt_local809729497_0001_r_000000_0/output/map_136.out.merged of size 453655910
17/10/20 09:58:19 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000129_0
17/10/20 09:58:19 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 6, commitMemory -> 174483098, usedMemory ->209379676
17/10/20 09:58:19 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000027_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:58:20 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000027_0
17/10/20 09:58:20 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 7, commitMemory -> 209379676, usedMemory ->244276254
17/10/20 09:58:20 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000078_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/20 09:58:20 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local809729497_0001_m_000078_0
17/10/20 09:58:20 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 8, commitMemory -> 244276254, usedMemory ->279172936
17/10/20 09:58:20 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000079_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:58:21 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000079_0
17/10/20 09:58:21 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 9, commitMemory -> 279172936, usedMemory ->314069514
17/10/20 09:58:21 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local809729497_0001_m_000130_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/20 09:58:21 INFO mapred.LocalJobRunner: reduce > copy task(attempt_local809729497_0001_m_000079_0 succeeded at 33279.98 MB/s) Aggregated copy rate(152 of 153 at 5044845.50 MB/s)
17/10/20 09:58:21 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local809729497_0001_m_000130_0
17/10/20 09:58:21 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 10, commitMemory -> 314069514, usedMemory ->348966092
17/10/20 09:58:21 INFO reduce.EventFetcher: EventFetcher is interrupted.. Returning
17/10/20 09:58:21 INFO mapred.LocalJobRunner: 153 / 153 copied.
17/10/20 09:58:21 INFO reduce.MergeManagerImpl: finalMerge called with 10 in-memory map-outputs and 11 on-disk map-outputs
17/10/20 09:58:21 INFO reduce.MergeManagerImpl: Keeping 10 segments, 348966092 bytes in memory for intermediate, on-disk merge
17/10/20 09:58:21 INFO reduce.MergeManagerImpl: Merging 11 files, 5324800086 bytes from disk
17/10/20 09:58:21 INFO reduce.MergeManagerImpl: Merging 0 segments, 0 bytes from memory into reduce
17/10/20 09:58:21 INFO mapred.Merger: Merging 21 sorted segments
17/10/20 09:58:21 INFO mapred.Merger: Merging 12 intermediate segments out of a total of 21
17/10/20 09:58:21 INFO mapreduce.Job:  map 100% reduce 33%
17/10/20 09:58:24 INFO mapred.LocalJobRunner: reduce > sort
17/10/20 09:58:24 INFO mapreduce.Job:  map 100% reduce 41%
17/10/20 09:58:27 INFO mapred.LocalJobRunner: reduce > sort
17/10/20 09:58:27 INFO mapreduce.Job:  map 100% reduce 47%
17/10/20 09:58:30 INFO mapred.LocalJobRunner: reduce > sort
17/10/20 09:58:30 INFO mapreduce.Job:  map 100% reduce 54%
17/10/20 09:58:33 INFO mapred.LocalJobRunner: reduce > sort
17/10/20 09:58:33 INFO mapreduce.Job:  map 100% reduce 61%
17/10/20 09:58:36 INFO mapred.Merger: Down to the last merge-pass, with 10 segments left of total size: 5324799890 bytes
17/10/20 09:58:36 INFO mapred.LocalJobRunner: reduce > sort
17/10/20 09:58:36 INFO Configuration.deprecation: mapred.skip.on is deprecated. Instead, use mapreduce.job.skiprecords
17/10/20 09:58:36 INFO mapred.LocalJobRunner: reduce > reduce
17/10/20 09:58:36 INFO mapreduce.Job:  map 100% reduce 67%
17/10/20 09:58:39 INFO mapred.LocalJobRunner: reduce > reduce
17/10/20 09:58:39 INFO mapreduce.Job:  map 100% reduce 68%
17/10/20 09:58:42 INFO mapred.LocalJobRunner: reduce > reduce
17/10/20 09:58:42 INFO mapreduce.Job:  map 100% reduce 69%
17/10/20 09:58:45 INFO mapred.LocalJobRunner: reduce > reduce
17/10/20 09:58:45 INFO mapreduce.Job:  map 100% reduce 71%
17/10/20 09:58:48 INFO mapred.LocalJobRunner: reduce > reduce
17/10/20 09:58:48 INFO mapreduce.Job:  map 100% reduce 72%
17/10/20 09:58:51 INFO mapred.LocalJobRunner: reduce > reduce
17/10/20 09:58:51 INFO mapreduce.Job:  map 100% reduce 73%
17/10/20 09:58:54 INFO mapred.LocalJobRunner: reduce > reduce
17/10/20 09:58:54 INFO mapreduce.Job:  map 100% reduce 74%
17/10/20 09:58:57 INFO mapred.LocalJobRunner: reduce > reduce
17/10/20 09:58:57 INFO mapreduce.Job:  map 100% reduce 76%
17/10/20 09:59:00 INFO mapred.LocalJobRunner: reduce > reduce
17/10/20 09:59:00 INFO mapreduce.Job:  map 100% reduce 77%
17/10/20 09:59:03 INFO mapred.LocalJobRunner: reduce > reduce
17/10/20 09:59:03 INFO mapreduce.Job:  map 100% reduce 78%
17/10/20 09:59:06 INFO mapred.LocalJobRunner: reduce > reduce
17/10/20 09:59:06 INFO mapreduce.Job:  map 100% reduce 80%
17/10/20 09:59:09 INFO mapred.LocalJobRunner: reduce > reduce
17/10/20 09:59:09 INFO mapreduce.Job:  map 100% reduce 81%
17/10/20 09:59:12 INFO mapred.LocalJobRunner: reduce > reduce
17/10/20 09:59:12 INFO mapreduce.Job:  map 100% reduce 82%
17/10/20 09:59:15 INFO mapred.LocalJobRunner: reduce > reduce
17/10/20 09:59:15 INFO mapreduce.Job:  map 100% reduce 84%
17/10/20 09:59:18 INFO mapred.LocalJobRunner: reduce > reduce
17/10/20 09:59:18 INFO mapreduce.Job:  map 100% reduce 85%
17/10/20 09:59:21 INFO mapred.LocalJobRunner: reduce > reduce
17/10/20 09:59:21 INFO mapreduce.Job:  map 100% reduce 86%
17/10/20 09:59:24 INFO mapred.LocalJobRunner: reduce > reduce
17/10/20 09:59:24 INFO mapreduce.Job:  map 100% reduce 87%
17/10/20 09:59:27 INFO mapred.LocalJobRunner: reduce > reduce
17/10/20 09:59:27 INFO mapreduce.Job:  map 100% reduce 88%
17/10/20 09:59:30 INFO mapred.LocalJobRunner: reduce > reduce
17/10/20 09:59:30 INFO mapreduce.Job:  map 100% reduce 90%
17/10/20 09:59:33 INFO mapred.LocalJobRunner: reduce > reduce
17/10/20 09:59:33 INFO mapreduce.Job:  map 100% reduce 91%
17/10/20 09:59:36 INFO mapred.LocalJobRunner: reduce > reduce
17/10/20 09:59:36 INFO mapreduce.Job:  map 100% reduce 92%
17/10/20 09:59:39 INFO mapred.LocalJobRunner: reduce > reduce
17/10/20 09:59:39 INFO mapreduce.Job:  map 100% reduce 94%
17/10/20 09:59:42 INFO mapred.LocalJobRunner: reduce > reduce
17/10/20 09:59:42 INFO mapreduce.Job:  map 100% reduce 95%
17/10/20 09:59:45 INFO mapred.LocalJobRunner: reduce > reduce
17/10/20 09:59:45 INFO mapreduce.Job:  map 100% reduce 96%
17/10/20 09:59:48 INFO mapred.LocalJobRunner: reduce > reduce
17/10/20 09:59:48 INFO mapreduce.Job:  map 100% reduce 97%
17/10/20 09:59:51 INFO mapred.LocalJobRunner: reduce > reduce
17/10/20 09:59:51 INFO mapreduce.Job:  map 100% reduce 99%
17/10/20 09:59:54 INFO mapred.LocalJobRunner: reduce > reduce
17/10/20 09:59:54 INFO mapreduce.Job:  map 100% reduce 100%
17/10/20 09:59:55 INFO mapred.Task: Task:attempt_local809729497_0001_r_000000_0 is done. And is in the process of committing
17/10/20 09:59:55 INFO mapred.LocalJobRunner: reduce > reduce
17/10/20 09:59:55 INFO mapred.Task: Task attempt_local809729497_0001_r_000000_0 is allowed to commit now
17/10/20 09:59:55 INFO output.FileOutputCommitter: Saved output of task 'attempt_local809729497_0001_r_000000_0' to file:/tmp/hsperfdata_ernest/ouput/tsort512m/_temporary/0/task_local809729497_0001_r_000000
17/10/20 09:59:55 INFO mapred.LocalJobRunner: reduce > reduce
17/10/20 09:59:55 INFO mapred.Task: Task 'attempt_local809729497_0001_r_000000_0' done.
17/10/20 09:59:55 INFO mapred.LocalJobRunner: Finishing task: attempt_local809729497_0001_r_000000_0
17/10/20 09:59:55 INFO mapred.LocalJobRunner: reduce task executor complete.
17/10/20 09:59:55 INFO mapreduce.Job: Job job_local809729497_0001 completed successfully
17/10/20 09:59:55 INFO mapreduce.Job: Counters: 30
        File System Counters
                FILE: Number of bytes read=416880059530
                FILE: Number of bytes written=427895516736
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
        Map-Reduce Framework
                Map input records=51200000
                Map output records=51200000
                Map output bytes=5222400000
                Map output materialized bytes=5324800918
                Input split bytes=18360
                Combine input records=0
                Combine output records=0
                Reduce input groups=51200000
                Reduce shuffle bytes=5324800918
                Reduce input records=51200000
                Reduce output records=51200000
                Spilled Records=110985871
                Shuffled Maps =153
                Failed Shuffles=0
                Merged Map outputs=153
                GC time elapsed (ms)=7511
                Total committed heap usage (bytes)=136515158016
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
        File Input Format Counters
                Bytes Read=5161818624
        File Output Format Counters
                Bytes Written=5160000008
17/10/20 09:59:55 INFO terasort.TeraSort: done

real    5m6.245s
user    4m28.116s
sys     0m31.350s
```