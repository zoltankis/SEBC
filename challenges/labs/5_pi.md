```
[siwicki@ip-172-32-1-58 root]$ time yarn jar /opt/cloudera/parcels/CDH/jars/hadoop-examples.jar pi 10 100
Number of Maps  = 10
Samples per Map = 100
Wrote input for Map #0
Wrote input for Map #1
Wrote input for Map #2
Wrote input for Map #3
Wrote input for Map #4
Wrote input for Map #5
Wrote input for Map #6
Wrote input for Map #7
Wrote input for Map #8
Wrote input for Map #9
Starting Job
17/10/20 10:07:29 INFO Configuration.deprecation: session.id is deprecated. Instead, use dfs.metrics.session-id
17/10/20 10:07:29 INFO jvm.JvmMetrics: Initializing JVM Metrics with processName=JobTracker, sessionId=
17/10/20 10:07:29 INFO input.FileInputFormat: Total input paths to process : 10
17/10/20 10:07:29 INFO mapreduce.JobSubmitter: number of splits:10
17/10/20 10:07:29 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_local1044813915_0001
17/10/20 10:07:30 INFO mapreduce.Job: The url to track the job: http://localhost:8080/
17/10/20 10:07:30 INFO mapreduce.Job: Running job: job_local1044813915_0001
17/10/20 10:07:30 INFO mapred.LocalJobRunner: OutputCommitter set in config null
17/10/20 10:07:30 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/20 10:07:30 INFO mapred.LocalJobRunner: OutputCommitter is org.apache.hadoop.mapreduce.lib.output.FileOutputCommitter
17/10/20 10:07:30 INFO mapred.LocalJobRunner: Waiting for map tasks
17/10/20 10:07:30 INFO mapred.LocalJobRunner: Starting task: attempt_local1044813915_0001_m_000000_0
17/10/20 10:07:30 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/20 10:07:30 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 10:07:30 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_siwicki/QuasiMonteCarlo_1508494049017_1975226879/in/part3:0+118
17/10/20 10:07:30 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 10:07:30 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 10:07:30 INFO mapred.MapTask: soft limit at 83886080
17/10/20 10:07:30 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 10:07:30 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 10:07:30 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/20 10:07:30 INFO mapred.LocalJobRunner:
17/10/20 10:07:30 INFO mapred.MapTask: Starting flush of map output
17/10/20 10:07:30 INFO mapred.MapTask: Spilling map output
17/10/20 10:07:30 INFO mapred.MapTask: bufstart = 0; bufend = 18; bufvoid = 104857600
17/10/20 10:07:30 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 26214392(104857568); length = 5/6553600
17/10/20 10:07:30 INFO mapred.MapTask: Finished spill 0
17/10/20 10:07:30 INFO mapred.Task: Task:attempt_local1044813915_0001_m_000000_0 is done. And is in the process of committing
17/10/20 10:07:30 INFO mapred.LocalJobRunner: map
17/10/20 10:07:30 INFO mapred.Task: Task 'attempt_local1044813915_0001_m_000000_0' done.
17/10/20 10:07:30 INFO mapred.LocalJobRunner: Finishing task: attempt_local1044813915_0001_m_000000_0
17/10/20 10:07:30 INFO mapred.LocalJobRunner: Starting task: attempt_local1044813915_0001_m_000001_0
17/10/20 10:07:30 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/20 10:07:30 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 10:07:30 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_siwicki/QuasiMonteCarlo_1508494049017_1975226879/in/part7:0+118
17/10/20 10:07:30 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 10:07:30 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 10:07:30 INFO mapred.MapTask: soft limit at 83886080
17/10/20 10:07:30 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 10:07:30 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 10:07:30 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/20 10:07:30 INFO mapred.LocalJobRunner:
17/10/20 10:07:30 INFO mapred.MapTask: Starting flush of map output
17/10/20 10:07:30 INFO mapred.MapTask: Spilling map output
17/10/20 10:07:30 INFO mapred.MapTask: bufstart = 0; bufend = 18; bufvoid = 104857600
17/10/20 10:07:30 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 26214392(104857568); length = 5/6553600
17/10/20 10:07:30 INFO mapred.MapTask: Finished spill 0
17/10/20 10:07:30 INFO mapred.Task: Task:attempt_local1044813915_0001_m_000001_0 is done. And is in the process of committing
17/10/20 10:07:30 INFO mapred.LocalJobRunner: map
17/10/20 10:07:30 INFO mapred.Task: Task 'attempt_local1044813915_0001_m_000001_0' done.
17/10/20 10:07:30 INFO mapred.LocalJobRunner: Finishing task: attempt_local1044813915_0001_m_000001_0
17/10/20 10:07:30 INFO mapred.LocalJobRunner: Starting task: attempt_local1044813915_0001_m_000002_0
17/10/20 10:07:30 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/20 10:07:30 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 10:07:30 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_siwicki/QuasiMonteCarlo_1508494049017_1975226879/in/part0:0+118
17/10/20 10:07:30 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 10:07:30 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 10:07:30 INFO mapred.MapTask: soft limit at 83886080
17/10/20 10:07:30 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 10:07:30 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 10:07:30 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/20 10:07:30 INFO mapred.LocalJobRunner:
17/10/20 10:07:30 INFO mapred.MapTask: Starting flush of map output
17/10/20 10:07:30 INFO mapred.MapTask: Spilling map output
17/10/20 10:07:30 INFO mapred.MapTask: bufstart = 0; bufend = 18; bufvoid = 104857600
17/10/20 10:07:30 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 26214392(104857568); length = 5/6553600
17/10/20 10:07:30 INFO mapred.MapTask: Finished spill 0
17/10/20 10:07:30 INFO mapred.Task: Task:attempt_local1044813915_0001_m_000002_0 is done. And is in the process of committing
17/10/20 10:07:30 INFO mapred.LocalJobRunner: map
17/10/20 10:07:30 INFO mapred.Task: Task 'attempt_local1044813915_0001_m_000002_0' done.
17/10/20 10:07:30 INFO mapred.LocalJobRunner: Finishing task: attempt_local1044813915_0001_m_000002_0
17/10/20 10:07:30 INFO mapred.LocalJobRunner: Starting task: attempt_local1044813915_0001_m_000003_0
17/10/20 10:07:30 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/20 10:07:30 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 10:07:30 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_siwicki/QuasiMonteCarlo_1508494049017_1975226879/in/part6:0+118
17/10/20 10:07:30 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 10:07:30 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 10:07:30 INFO mapred.MapTask: soft limit at 83886080
17/10/20 10:07:30 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 10:07:30 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 10:07:30 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/20 10:07:30 INFO mapred.LocalJobRunner:
17/10/20 10:07:30 INFO mapred.MapTask: Starting flush of map output
17/10/20 10:07:30 INFO mapred.MapTask: Spilling map output
17/10/20 10:07:30 INFO mapred.MapTask: bufstart = 0; bufend = 18; bufvoid = 104857600
17/10/20 10:07:30 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 26214392(104857568); length = 5/6553600
17/10/20 10:07:30 INFO mapred.MapTask: Finished spill 0
17/10/20 10:07:30 INFO mapred.Task: Task:attempt_local1044813915_0001_m_000003_0 is done. And is in the process of committing
17/10/20 10:07:30 INFO mapred.LocalJobRunner: map
17/10/20 10:07:30 INFO mapred.Task: Task 'attempt_local1044813915_0001_m_000003_0' done.
17/10/20 10:07:30 INFO mapred.LocalJobRunner: Finishing task: attempt_local1044813915_0001_m_000003_0
17/10/20 10:07:30 INFO mapred.LocalJobRunner: Starting task: attempt_local1044813915_0001_m_000004_0
17/10/20 10:07:30 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/20 10:07:30 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 10:07:30 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_siwicki/QuasiMonteCarlo_1508494049017_1975226879/in/part8:0+118
17/10/20 10:07:30 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 10:07:30 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 10:07:30 INFO mapred.MapTask: soft limit at 83886080
17/10/20 10:07:30 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 10:07:30 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 10:07:30 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/20 10:07:30 INFO mapred.LocalJobRunner:
17/10/20 10:07:30 INFO mapred.MapTask: Starting flush of map output
17/10/20 10:07:30 INFO mapred.MapTask: Spilling map output
17/10/20 10:07:30 INFO mapred.MapTask: bufstart = 0; bufend = 18; bufvoid = 104857600
17/10/20 10:07:30 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 26214392(104857568); length = 5/6553600
17/10/20 10:07:30 INFO mapred.MapTask: Finished spill 0
17/10/20 10:07:30 INFO mapred.Task: Task:attempt_local1044813915_0001_m_000004_0 is done. And is in the process of committing
17/10/20 10:07:30 INFO mapred.LocalJobRunner: map
17/10/20 10:07:30 INFO mapred.Task: Task 'attempt_local1044813915_0001_m_000004_0' done.
17/10/20 10:07:30 INFO mapred.LocalJobRunner: Finishing task: attempt_local1044813915_0001_m_000004_0
17/10/20 10:07:30 INFO mapred.LocalJobRunner: Starting task: attempt_local1044813915_0001_m_000005_0
17/10/20 10:07:30 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/20 10:07:30 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 10:07:30 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_siwicki/QuasiMonteCarlo_1508494049017_1975226879/in/part1:0+118
17/10/20 10:07:30 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 10:07:30 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 10:07:30 INFO mapred.MapTask: soft limit at 83886080
17/10/20 10:07:30 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 10:07:30 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 10:07:30 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/20 10:07:30 INFO mapred.LocalJobRunner:
17/10/20 10:07:30 INFO mapred.MapTask: Starting flush of map output
17/10/20 10:07:30 INFO mapred.MapTask: Spilling map output
17/10/20 10:07:30 INFO mapred.MapTask: bufstart = 0; bufend = 18; bufvoid = 104857600
17/10/20 10:07:30 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 26214392(104857568); length = 5/6553600
17/10/20 10:07:30 INFO mapred.MapTask: Finished spill 0
17/10/20 10:07:30 INFO mapred.Task: Task:attempt_local1044813915_0001_m_000005_0 is done. And is in the process of committing
17/10/20 10:07:30 INFO mapred.LocalJobRunner: map
17/10/20 10:07:30 INFO mapred.Task: Task 'attempt_local1044813915_0001_m_000005_0' done.
17/10/20 10:07:30 INFO mapred.LocalJobRunner: Finishing task: attempt_local1044813915_0001_m_000005_0
17/10/20 10:07:30 INFO mapred.LocalJobRunner: Starting task: attempt_local1044813915_0001_m_000006_0
17/10/20 10:07:30 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/20 10:07:30 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 10:07:30 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_siwicki/QuasiMonteCarlo_1508494049017_1975226879/in/part2:0+118
17/10/20 10:07:30 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 10:07:30 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 10:07:30 INFO mapred.MapTask: soft limit at 83886080
17/10/20 10:07:30 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 10:07:30 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 10:07:30 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/20 10:07:30 INFO mapred.LocalJobRunner:
17/10/20 10:07:30 INFO mapred.MapTask: Starting flush of map output
17/10/20 10:07:30 INFO mapred.MapTask: Spilling map output
17/10/20 10:07:30 INFO mapred.MapTask: bufstart = 0; bufend = 18; bufvoid = 104857600
17/10/20 10:07:30 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 26214392(104857568); length = 5/6553600
17/10/20 10:07:30 INFO mapred.MapTask: Finished spill 0
17/10/20 10:07:30 INFO mapred.Task: Task:attempt_local1044813915_0001_m_000006_0 is done. And is in the process of committing
17/10/20 10:07:30 INFO mapred.LocalJobRunner: map
17/10/20 10:07:30 INFO mapred.Task: Task 'attempt_local1044813915_0001_m_000006_0' done.
17/10/20 10:07:30 INFO mapred.LocalJobRunner: Finishing task: attempt_local1044813915_0001_m_000006_0
17/10/20 10:07:30 INFO mapred.LocalJobRunner: Starting task: attempt_local1044813915_0001_m_000007_0
17/10/20 10:07:30 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/20 10:07:30 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 10:07:30 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_siwicki/QuasiMonteCarlo_1508494049017_1975226879/in/part5:0+118
17/10/20 10:07:30 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 10:07:30 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 10:07:30 INFO mapred.MapTask: soft limit at 83886080
17/10/20 10:07:30 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 10:07:30 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 10:07:30 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/20 10:07:30 INFO mapred.LocalJobRunner:
17/10/20 10:07:30 INFO mapred.MapTask: Starting flush of map output
17/10/20 10:07:30 INFO mapred.MapTask: Spilling map output
17/10/20 10:07:30 INFO mapred.MapTask: bufstart = 0; bufend = 18; bufvoid = 104857600
17/10/20 10:07:30 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 26214392(104857568); length = 5/6553600
17/10/20 10:07:30 INFO mapred.MapTask: Finished spill 0
17/10/20 10:07:30 INFO mapred.Task: Task:attempt_local1044813915_0001_m_000007_0 is done. And is in the process of committing
17/10/20 10:07:30 INFO mapred.LocalJobRunner: map
17/10/20 10:07:30 INFO mapred.Task: Task 'attempt_local1044813915_0001_m_000007_0' done.
17/10/20 10:07:30 INFO mapred.LocalJobRunner: Finishing task: attempt_local1044813915_0001_m_000007_0
17/10/20 10:07:30 INFO mapred.LocalJobRunner: Starting task: attempt_local1044813915_0001_m_000008_0
17/10/20 10:07:30 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/20 10:07:30 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 10:07:30 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_siwicki/QuasiMonteCarlo_1508494049017_1975226879/in/part4:0+118
17/10/20 10:07:30 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 10:07:30 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 10:07:30 INFO mapred.MapTask: soft limit at 83886080
17/10/20 10:07:30 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 10:07:30 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 10:07:30 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/20 10:07:30 INFO mapred.LocalJobRunner:
17/10/20 10:07:30 INFO mapred.MapTask: Starting flush of map output
17/10/20 10:07:30 INFO mapred.MapTask: Spilling map output
17/10/20 10:07:30 INFO mapred.MapTask: bufstart = 0; bufend = 18; bufvoid = 104857600
17/10/20 10:07:30 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 26214392(104857568); length = 5/6553600
17/10/20 10:07:30 INFO mapred.MapTask: Finished spill 0
17/10/20 10:07:30 INFO mapred.Task: Task:attempt_local1044813915_0001_m_000008_0 is done. And is in the process of committing
17/10/20 10:07:30 INFO mapred.LocalJobRunner: map
17/10/20 10:07:30 INFO mapred.Task: Task 'attempt_local1044813915_0001_m_000008_0' done.
17/10/20 10:07:30 INFO mapred.LocalJobRunner: Finishing task: attempt_local1044813915_0001_m_000008_0
17/10/20 10:07:30 INFO mapred.LocalJobRunner: Starting task: attempt_local1044813915_0001_m_000009_0
17/10/20 10:07:30 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/20 10:07:30 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 10:07:30 INFO mapred.MapTask: Processing split: file:/tmp/hsperfdata_siwicki/QuasiMonteCarlo_1508494049017_1975226879/in/part9:0+118
17/10/20 10:07:30 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/20 10:07:30 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/20 10:07:30 INFO mapred.MapTask: soft limit at 83886080
17/10/20 10:07:30 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/20 10:07:30 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/20 10:07:30 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/20 10:07:30 INFO mapred.LocalJobRunner:
17/10/20 10:07:30 INFO mapred.MapTask: Starting flush of map output
17/10/20 10:07:30 INFO mapred.MapTask: Spilling map output
17/10/20 10:07:30 INFO mapred.MapTask: bufstart = 0; bufend = 18; bufvoid = 104857600
17/10/20 10:07:30 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 26214392(104857568); length = 5/6553600
17/10/20 10:07:30 INFO mapred.MapTask: Finished spill 0
17/10/20 10:07:30 INFO mapred.Task: Task:attempt_local1044813915_0001_m_000009_0 is done. And is in the process of committing
17/10/20 10:07:30 INFO mapred.LocalJobRunner: map
17/10/20 10:07:30 INFO mapred.Task: Task 'attempt_local1044813915_0001_m_000009_0' done.
17/10/20 10:07:30 INFO mapred.LocalJobRunner: Finishing task: attempt_local1044813915_0001_m_000009_0
17/10/20 10:07:30 INFO mapred.LocalJobRunner: map task executor complete.
17/10/20 10:07:30 INFO mapred.LocalJobRunner: Waiting for reduce tasks
17/10/20 10:07:30 INFO mapred.LocalJobRunner: Starting task: attempt_local1044813915_0001_r_000000_0
17/10/20 10:07:30 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/20 10:07:30 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/20 10:07:30 INFO mapred.ReduceTask: Using ShuffleConsumerPlugin: org.apache.hadoop.mapreduce.task.reduce.Shuffle@5a52ab11
17/10/20 10:07:31 INFO reduce.MergeManagerImpl: MergerManager: memoryLimit=652528832, maxSingleShuffleLimit=163132208, mergeThreshold=430669056, ioSortFactor=10, memToMemMergeOutputsThreshold=10
17/10/20 10:07:31 INFO reduce.EventFetcher: attempt_local1044813915_0001_r_000000_0 Thread started: EventFetcher for fetching Map Completion Events
17/10/20 10:07:31 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local1044813915_0001_m_000009_0 decomp: 24 len: 28 to MEMORY
17/10/20 10:07:31 INFO reduce.InMemoryMapOutput: Read 24 bytes from map-output for attempt_local1044813915_0001_m_000009_0
17/10/20 10:07:31 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 24, inMemoryMapOutputs.size() -> 1, commitMemory -> 0, usedMemory ->24
17/10/20 10:07:31 INFO mapreduce.Job: Job job_local1044813915_0001 running in uber mode : false
17/10/20 10:07:31 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local1044813915_0001_m_000006_0 decomp: 24 len: 28 to MEMORY
17/10/20 10:07:31 INFO mapreduce.Job:  map 100% reduce 0%
17/10/20 10:07:31 INFO reduce.InMemoryMapOutput: Read 24 bytes from map-output for attempt_local1044813915_0001_m_000006_0
17/10/20 10:07:31 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 24, inMemoryMapOutputs.size() -> 2, commitMemory -> 24, usedMemory ->48
17/10/20 10:07:31 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local1044813915_0001_m_000003_0 decomp: 24 len: 28 to MEMORY
17/10/20 10:07:31 INFO reduce.InMemoryMapOutput: Read 24 bytes from map-output for attempt_local1044813915_0001_m_000003_0
17/10/20 10:07:31 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 24, inMemoryMapOutputs.size() -> 3, commitMemory -> 48, usedMemory ->72
17/10/20 10:07:31 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local1044813915_0001_m_000000_0 decomp: 24 len: 28 to MEMORY
17/10/20 10:07:31 INFO reduce.InMemoryMapOutput: Read 24 bytes from map-output for attempt_local1044813915_0001_m_000000_0
17/10/20 10:07:31 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 24, inMemoryMapOutputs.size() -> 4, commitMemory -> 72, usedMemory ->96
17/10/20 10:07:31 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local1044813915_0001_m_000005_0 decomp: 24 len: 28 to MEMORY
17/10/20 10:07:31 INFO reduce.InMemoryMapOutput: Read 24 bytes from map-output for attempt_local1044813915_0001_m_000005_0
17/10/20 10:07:31 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 24, inMemoryMapOutputs.size() -> 5, commitMemory -> 96, usedMemory ->120
17/10/20 10:07:31 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local1044813915_0001_m_000002_0 decomp: 24 len: 28 to MEMORY
17/10/20 10:07:31 INFO reduce.InMemoryMapOutput: Read 24 bytes from map-output for attempt_local1044813915_0001_m_000002_0
17/10/20 10:07:31 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 24, inMemoryMapOutputs.size() -> 6, commitMemory -> 120, usedMemory ->144
17/10/20 10:07:31 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local1044813915_0001_m_000001_0 decomp: 24 len: 28 to MEMORY
17/10/20 10:07:31 INFO reduce.InMemoryMapOutput: Read 24 bytes from map-output for attempt_local1044813915_0001_m_000001_0
17/10/20 10:07:31 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 24, inMemoryMapOutputs.size() -> 7, commitMemory -> 144, usedMemory ->168
17/10/20 10:07:31 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local1044813915_0001_m_000008_0 decomp: 24 len: 28 to MEMORY
17/10/20 10:07:31 INFO reduce.InMemoryMapOutput: Read 24 bytes from map-output for attempt_local1044813915_0001_m_000008_0
17/10/20 10:07:31 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 24, inMemoryMapOutputs.size() -> 8, commitMemory -> 168, usedMemory ->192
17/10/20 10:07:31 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local1044813915_0001_m_000007_0 decomp: 24 len: 28 to MEMORY
17/10/20 10:07:31 INFO reduce.InMemoryMapOutput: Read 24 bytes from map-output for attempt_local1044813915_0001_m_000007_0
17/10/20 10:07:31 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 24, inMemoryMapOutputs.size() -> 9, commitMemory -> 192, usedMemory ->216
17/10/20 10:07:31 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local1044813915_0001_m_000004_0 decomp: 24 len: 28 to MEMORY
17/10/20 10:07:31 INFO reduce.InMemoryMapOutput: Read 24 bytes from map-output for attempt_local1044813915_0001_m_000004_0
17/10/20 10:07:31 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 24, inMemoryMapOutputs.size() -> 10, commitMemory -> 216, usedMemory ->240
17/10/20 10:07:31 INFO reduce.EventFetcher: EventFetcher is interrupted.. Returning
17/10/20 10:07:31 INFO mapred.LocalJobRunner: 10 / 10 copied.
17/10/20 10:07:31 INFO reduce.MergeManagerImpl: finalMerge called with 10 in-memory map-outputs and 0 on-disk map-outputs
17/10/20 10:07:31 INFO mapred.Merger: Merging 10 sorted segments
17/10/20 10:07:31 INFO mapred.Merger: Down to the last merge-pass, with 10 segments left of total size: 210 bytes
17/10/20 10:07:31 INFO reduce.MergeManagerImpl: Merged 10 segments, 240 bytes to disk to satisfy reduce memory limit
17/10/20 10:07:31 INFO reduce.MergeManagerImpl: Merging 1 files, 226 bytes from disk
17/10/20 10:07:31 INFO reduce.MergeManagerImpl: Merging 0 segments, 0 bytes from memory into reduce
17/10/20 10:07:31 INFO mapred.Merger: Merging 1 sorted segments
17/10/20 10:07:31 INFO mapred.Merger: Down to the last merge-pass, with 1 segments left of total size: 219 bytes
17/10/20 10:07:31 INFO mapred.LocalJobRunner: 10 / 10 copied.
17/10/20 10:07:31 INFO Configuration.deprecation: mapred.skip.on is deprecated. Instead, use mapreduce.job.skiprecords
17/10/20 10:07:31 INFO mapred.Task: Task:attempt_local1044813915_0001_r_000000_0 is done. And is in the process of committing
17/10/20 10:07:31 INFO mapred.LocalJobRunner: 10 / 10 copied.
17/10/20 10:07:31 INFO mapred.Task: Task attempt_local1044813915_0001_r_000000_0 is allowed to commit now
17/10/20 10:07:31 INFO output.FileOutputCommitter: Saved output of task 'attempt_local1044813915_0001_r_000000_0' to file:/tmp/hsperfdata_siwicki/QuasiMonteCarlo_1508494049017_1975226879/out/_temporary/0/task_local1044813915_0001_r_000000
17/10/20 10:07:31 INFO mapred.LocalJobRunner: reduce > reduce
17/10/20 10:07:31 INFO mapred.Task: Task 'attempt_local1044813915_0001_r_000000_0' done.
17/10/20 10:07:31 INFO mapred.LocalJobRunner: Finishing task: attempt_local1044813915_0001_r_000000_0
17/10/20 10:07:31 INFO mapred.LocalJobRunner: reduce task executor complete.
17/10/20 10:07:32 INFO mapreduce.Job:  map 100% reduce 100%
17/10/20 10:07:32 INFO mapreduce.Job: Job job_local1044813915_0001 completed successfully
17/10/20 10:07:32 INFO mapreduce.Job: Counters: 30
        File System Counters
                FILE: Number of bytes read=3127722
                FILE: Number of bytes written=6243389
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
        Map-Reduce Framework
                Map input records=10
                Map output records=20
                Map output bytes=180
                Map output materialized bytes=280
                Input split bytes=1430
                Combine input records=0
                Combine output records=0
                Reduce input groups=2
                Reduce shuffle bytes=280
                Reduce input records=20
                Reduce output records=0
                Spilled Records=40
                Shuffled Maps =10
                Failed Shuffles=0
                Merged Map outputs=10
                GC time elapsed (ms)=250
                Total committed heap usage (bytes)=4833935360
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
        File Input Format Counters
                Bytes Read=1300
        File Output Format Counters
                Bytes Written=109
Job Finished in 2.609 seconds
Estimated value of Pi is 3.14800000000000000000

real    0m4.055s
user    0m6.422s
sys     0m0.849s

```