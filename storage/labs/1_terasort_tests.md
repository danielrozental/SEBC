# 1. Agrego usuario en todos los nodos

sudo useradd danielrozental
sudo su hdfs
hdfs dfs -mkdir /user/danielrozental

hdfs dfs -chown danielrozental /user/danielrozental

sudo su danielrozental

# 2. teragen

Lo corro con 1 GB en vez de 10 GB.

time hadoop jar /disco1/cloudera/parcels/CDH/jars/hadoop-examples.jar teragen -Dmapred.map.tasks=4 -Ddfs.block.size=33554432 10737418 /user/danielrozental/teragen

```
[danielrozental@ip-172-31-11-253 centos]$ time hadoop jar /disco1/cloudera/parcels/CDH/jars/hadoop-examples.jar teragen -Dmapred.map.tasks=4 -Ddfs.block.size=33554432 10737418 /user/danielrozental/teragen
17/10/03 15:03:19 INFO Configuration.deprecation: session.id is deprecated. Instead, use dfs.metrics.session-id
17/10/03 15:03:19 INFO jvm.JvmMetrics: Initializing JVM Metrics with processName=JobTracker, sessionId=
17/10/03 15:03:19 INFO terasort.TeraSort: Generating 10737418 using 1
17/10/03 15:03:19 INFO mapreduce.JobSubmitter: number of splits:1
17/10/03 15:03:19 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
17/10/03 15:03:19 INFO Configuration.deprecation: dfs.block.size is deprecated. Instead, use dfs.blocksize
17/10/03 15:03:19 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_local2124604494_0001
17/10/03 15:03:19 INFO mapreduce.Job: The url to track the job: http://localhost:8080/
17/10/03 15:03:19 INFO mapreduce.Job: Running job: job_local2124604494_0001
17/10/03 15:03:19 INFO mapred.LocalJobRunner: OutputCommitter set in config null
17/10/03 15:03:19 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/03 15:03:19 INFO mapred.LocalJobRunner: OutputCommitter is org.apache.hadoop.mapreduce.lib.output.FileOutputCommitter
17/10/03 15:03:19 INFO mapred.LocalJobRunner: Waiting for map tasks
17/10/03 15:03:19 INFO mapred.LocalJobRunner: Starting task: attempt_local2124604494_0001_m_000000_0
17/10/03 15:03:19 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/03 15:03:19 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/03 15:03:19 INFO mapred.MapTask: Processing split: org.apache.hadoop.examples.terasort.TeraGen$RangeInputFormat$RangeInputSplit@10e9445b
17/10/03 15:03:20 INFO mapreduce.Job: Job job_local2124604494_0001 running in uber mode : false
17/10/03 15:03:20 INFO mapreduce.Job:  map 0% reduce 0%
17/10/03 15:03:25 INFO mapred.LocalJobRunner: map > map
17/10/03 15:03:26 INFO mapreduce.Job:  map 55% reduce 0%
17/10/03 15:03:28 INFO mapred.LocalJobRunner: map > map
17/10/03 15:03:29 INFO mapreduce.Job:  map 85% reduce 0%
17/10/03 15:03:30 INFO mapred.LocalJobRunner: map > map
17/10/03 15:03:30 INFO mapred.Task: Task:attempt_local2124604494_0001_m_000000_0 is done. And is in the process of committing
17/10/03 15:03:30 INFO mapred.LocalJobRunner: map > map
17/10/03 15:03:30 INFO mapred.Task: Task attempt_local2124604494_0001_m_000000_0 is allowed to commit now
17/10/03 15:03:30 INFO output.FileOutputCommitter: Saved output of task 'attempt_local2124604494_0001_m_000000_0' to hdfs://ip-172-31-1-236.us-east-2.compute.internal:8020/user/danielrozental/teragen/_temporary/0/task_local2124604494_0001_m_000000
17/10/03 15:03:30 INFO mapred.LocalJobRunner: map
17/10/03 15:03:30 INFO mapred.Task: Task 'attempt_local2124604494_0001_m_000000_0' done.
17/10/03 15:03:30 INFO mapred.LocalJobRunner: Finishing task: attempt_local2124604494_0001_m_000000_0
17/10/03 15:03:30 INFO mapred.LocalJobRunner: map task executor complete.
17/10/03 15:03:30 INFO mapreduce.Job:  map 100% reduce 0%
17/10/03 15:03:30 INFO mapreduce.Job: Job job_local2124604494_0001 completed successfully
17/10/03 15:03:30 INFO mapreduce.Job: Counters: 21
        File System Counters
                FILE: Number of bytes read=276332
                FILE: Number of bytes written=581213
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=0
                HDFS: Number of bytes written=1073741800
                HDFS: Number of read operations=4
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=3
        Map-Reduce Framework
                Map input records=10737418
                Map output records=10737418
                Input split bytes=82
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=125
                Total committed heap usage (bytes)=227016704
        org.apache.hadoop.examples.terasort.TeraGen$Counters
                CHECKSUM=23055106908592388
        File Input Format Counters
                Bytes Read=0
        File Output Format Counters
                Bytes Written=1073741800

real    0m13.516s
user    0m19.005s
sys     0m0.479s
```

# 3. terasort

time hadoop jar /disco1/cloudera/parcels/CDH/jars/hadoop-examples.jar terasort /user/danielrozental/teragen /user/danielrozental/terasort


```
[danielrozental@ip-172-31-11-253 centos]$ time hadoop jar /disco1/cloudera/parcels/CDH/jars/hadoop-examples.jar terasort /user/danielrozental/teragen /user/danielrozental/terasort
17/10/03 15:04:05 INFO terasort.TeraSort: starting
17/10/03 15:04:06 INFO input.FileInputFormat: Total input paths to process : 1
Spent 127ms computing base-splits.
Spent 2ms computing TeraScheduler splits.
Computing input splits took 129ms
Sampling 10 splits of 32
Making 1 from 100000 sampled records
Computing parititions took 489ms
Spent 621ms computing partitions.
17/10/03 15:04:06 INFO Configuration.deprecation: session.id is deprecated. Instead, use dfs.metrics.session-id
17/10/03 15:04:06 INFO jvm.JvmMetrics: Initializing JVM Metrics with processName=JobTracker, sessionId=
17/10/03 15:04:07 INFO mapreduce.JobSubmitter: number of splits:32
17/10/03 15:04:07 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_local662000802_0001
17/10/03 15:04:07 INFO mapred.LocalDistributedCacheManager: Creating symlink: /tmp/hadoop-danielrozental/mapred/local/1507043047320/_partition.lst <- /home/centos/_partition.lst
17/10/03 15:04:07 WARN fs.FileUtil: Command 'ln -s /tmp/hadoop-danielrozental/mapred/local/1507043047320/_partition.lst /home/centos/_partition.lst' failed 1 with: ln: failed to access ‘/home/centos/_partition.lst’: Permission denied

17/10/03 15:04:07 WARN mapred.LocalDistributedCacheManager: Failed to create symlink: /tmp/hadoop-danielrozental/mapred/local/1507043047320/_partition.lst <- /home/centos/_partition.lst
17/10/03 15:04:07 INFO mapred.LocalDistributedCacheManager: Localized hdfs://ip-172-31-1-236.us-east-2.compute.internal:8020/user/danielrozental/terasort/_partition.lst as file:/tmp/hadoop-danielrozental/mapred/local/1507043047320/_partition.lst
17/10/03 15:04:07 INFO mapreduce.Job: The url to track the job: http://localhost:8080/
17/10/03 15:04:07 INFO mapreduce.Job: Running job: job_local662000802_0001
17/10/03 15:04:07 INFO mapred.LocalJobRunner: OutputCommitter set in config null
17/10/03 15:04:07 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/03 15:04:07 INFO mapred.LocalJobRunner: OutputCommitter is org.apache.hadoop.mapreduce.lib.output.FileOutputCommitter
17/10/03 15:04:07 INFO mapred.LocalJobRunner: Waiting for map tasks
17/10/03 15:04:07 INFO mapred.LocalJobRunner: Starting task: attempt_local662000802_0001_m_000000_0
17/10/03 15:04:07 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/03 15:04:07 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/03 15:04:07 INFO mapred.MapTask: Processing split: hdfs://ip-172-31-1-236.us-east-2.compute.internal:8020/user/danielrozental/teragen/part-m-00000:0+33554432
17/10/03 15:04:07 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/03 15:04:07 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/03 15:04:07 INFO mapred.MapTask: soft limit at 83886080
17/10/03 15:04:07 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/03 15:04:07 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/03 15:04:07 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/03 15:04:08 INFO mapred.LocalJobRunner:
17/10/03 15:04:08 INFO mapred.MapTask: Starting flush of map output
17/10/03 15:04:08 INFO mapred.MapTask: Spilling map output
17/10/03 15:04:08 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/03 15:04:08 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(99488880); length = 1342177/6553600
17/10/03 15:04:08 INFO mapreduce.Job: Job job_local662000802_0001 running in uber mode : false
17/10/03 15:04:08 INFO mapreduce.Job:  map 0% reduce 0%
17/10/03 15:04:09 INFO mapred.MapTask: Finished spill 0
17/10/03 15:04:09 INFO mapred.Task: Task:attempt_local662000802_0001_m_000000_0 is done. And is in the process of committing
17/10/03 15:04:09 INFO mapred.LocalJobRunner: map
17/10/03 15:04:09 INFO mapred.Task: Task 'attempt_local662000802_0001_m_000000_0' done.
17/10/03 15:04:09 INFO mapred.LocalJobRunner: Finishing task: attempt_local662000802_0001_m_000000_0
17/10/03 15:04:09 INFO mapred.LocalJobRunner: Starting task: attempt_local662000802_0001_m_000001_0
17/10/03 15:04:09 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/03 15:04:09 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/03 15:04:09 INFO mapred.MapTask: Processing split: hdfs://ip-172-31-1-236.us-east-2.compute.internal:8020/user/danielrozental/teragen/part-m-00000:33554432+33554432
17/10/03 15:04:09 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/03 15:04:09 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/03 15:04:09 INFO mapred.MapTask: soft limit at 83886080
17/10/03 15:04:09 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/03 15:04:09 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/03 15:04:09 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/03 15:04:09 INFO mapreduce.Job:  map 100% reduce 0%
17/10/03 15:04:09 INFO mapred.LocalJobRunner:
17/10/03 15:04:09 INFO mapred.MapTask: Starting flush of map output
17/10/03 15:04:09 INFO mapred.MapTask: Spilling map output
17/10/03 15:04:09 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/03 15:04:09 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(99488896); length = 1342173/6553600
17/10/03 15:04:10 INFO mapred.MapTask: Finished spill 0
17/10/03 15:04:10 INFO mapred.Task: Task:attempt_local662000802_0001_m_000001_0 is done. And is in the process of committing
17/10/03 15:04:10 INFO mapred.LocalJobRunner: map
17/10/03 15:04:10 INFO mapred.Task: Task 'attempt_local662000802_0001_m_000001_0' done.
17/10/03 15:04:10 INFO mapred.LocalJobRunner: Finishing task: attempt_local662000802_0001_m_000001_0
17/10/03 15:04:10 INFO mapred.LocalJobRunner: Starting task: attempt_local662000802_0001_m_000002_0
17/10/03 15:04:10 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/03 15:04:10 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/03 15:04:10 INFO mapred.MapTask: Processing split: hdfs://ip-172-31-1-236.us-east-2.compute.internal:8020/user/danielrozental/teragen/part-m-00000:67108864+33554432
17/10/03 15:04:10 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/03 15:04:10 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/03 15:04:10 INFO mapred.MapTask: soft limit at 83886080
17/10/03 15:04:10 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/03 15:04:10 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/03 15:04:10 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/03 15:04:10 INFO mapred.LocalJobRunner:
17/10/03 15:04:10 INFO mapred.MapTask: Starting flush of map output
17/10/03 15:04:10 INFO mapred.MapTask: Spilling map output
17/10/03 15:04:10 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/03 15:04:10 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(99488896); length = 1342173/6553600
17/10/03 15:04:11 INFO mapred.MapTask: Finished spill 0
17/10/03 15:04:11 INFO mapred.Task: Task:attempt_local662000802_0001_m_000002_0 is done. And is in the process of committing
17/10/03 15:04:11 INFO mapred.LocalJobRunner: map
17/10/03 15:04:11 INFO mapred.Task: Task 'attempt_local662000802_0001_m_000002_0' done.
17/10/03 15:04:11 INFO mapred.LocalJobRunner: Finishing task: attempt_local662000802_0001_m_000002_0
17/10/03 15:04:11 INFO mapred.LocalJobRunner: Starting task: attempt_local662000802_0001_m_000003_0
17/10/03 15:04:11 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/03 15:04:11 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/03 15:04:11 INFO mapred.MapTask: Processing split: hdfs://ip-172-31-1-236.us-east-2.compute.internal:8020/user/danielrozental/teragen/part-m-00000:100663296+33554432
17/10/03 15:04:11 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/03 15:04:11 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/03 15:04:11 INFO mapred.MapTask: soft limit at 83886080
17/10/03 15:04:11 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/03 15:04:11 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/03 15:04:11 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/03 15:04:11 INFO mapred.LocalJobRunner:
17/10/03 15:04:11 INFO mapred.MapTask: Starting flush of map output
17/10/03 15:04:11 INFO mapred.MapTask: Spilling map output
17/10/03 15:04:11 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/03 15:04:11 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(99488880); length = 1342177/6553600
17/10/03 15:04:12 INFO mapred.MapTask: Finished spill 0
17/10/03 15:04:12 INFO mapred.Task: Task:attempt_local662000802_0001_m_000003_0 is done. And is in the process of committing
17/10/03 15:04:12 INFO mapred.LocalJobRunner: map
17/10/03 15:04:12 INFO mapred.Task: Task 'attempt_local662000802_0001_m_000003_0' done.
17/10/03 15:04:12 INFO mapred.LocalJobRunner: Finishing task: attempt_local662000802_0001_m_000003_0
17/10/03 15:04:12 INFO mapred.LocalJobRunner: Starting task: attempt_local662000802_0001_m_000004_0
17/10/03 15:04:12 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/03 15:04:12 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/03 15:04:12 INFO mapred.MapTask: Processing split: hdfs://ip-172-31-1-236.us-east-2.compute.internal:8020/user/danielrozental/teragen/part-m-00000:134217728+33554432
17/10/03 15:04:12 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/03 15:04:12 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/03 15:04:12 INFO mapred.MapTask: soft limit at 83886080
17/10/03 15:04:12 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/03 15:04:12 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/03 15:04:12 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/03 15:04:12 INFO mapred.LocalJobRunner:
17/10/03 15:04:12 INFO mapred.MapTask: Starting flush of map output
17/10/03 15:04:12 INFO mapred.MapTask: Spilling map output
17/10/03 15:04:12 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/03 15:04:12 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(99488896); length = 1342173/6553600
17/10/03 15:04:12 INFO mapreduce.Job:  map 13% reduce 0%
17/10/03 15:04:13 INFO mapred.MapTask: Finished spill 0
17/10/03 15:04:13 INFO mapred.Task: Task:attempt_local662000802_0001_m_000004_0 is done. And is in the process of committing
17/10/03 15:04:13 INFO mapred.LocalJobRunner: map
17/10/03 15:04:13 INFO mapred.Task: Task 'attempt_local662000802_0001_m_000004_0' done.
17/10/03 15:04:13 INFO mapred.LocalJobRunner: Finishing task: attempt_local662000802_0001_m_000004_0
17/10/03 15:04:13 INFO mapred.LocalJobRunner: Starting task: attempt_local662000802_0001_m_000005_0
17/10/03 15:04:13 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/03 15:04:13 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/03 15:04:13 INFO mapred.MapTask: Processing split: hdfs://ip-172-31-1-236.us-east-2.compute.internal:8020/user/danielrozental/teragen/part-m-00000:167772160+33554432
17/10/03 15:04:13 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/03 15:04:13 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/03 15:04:13 INFO mapred.MapTask: soft limit at 83886080
17/10/03 15:04:13 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/03 15:04:13 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/03 15:04:13 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/03 15:04:13 INFO mapred.LocalJobRunner:
17/10/03 15:04:13 INFO mapred.MapTask: Starting flush of map output
17/10/03 15:04:13 INFO mapred.MapTask: Spilling map output
17/10/03 15:04:13 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/03 15:04:13 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(99488896); length = 1342173/6553600
17/10/03 15:04:13 INFO mapreduce.Job:  map 16% reduce 0%
17/10/03 15:04:14 INFO mapred.MapTask: Finished spill 0
17/10/03 15:04:14 INFO mapred.Task: Task:attempt_local662000802_0001_m_000005_0 is done. And is in the process of committing
17/10/03 15:04:14 INFO mapred.LocalJobRunner: map
17/10/03 15:04:14 INFO mapred.Task: Task 'attempt_local662000802_0001_m_000005_0' done.
17/10/03 15:04:14 INFO mapred.LocalJobRunner: Finishing task: attempt_local662000802_0001_m_000005_0
17/10/03 15:04:14 INFO mapred.LocalJobRunner: Starting task: attempt_local662000802_0001_m_000006_0
17/10/03 15:04:14 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/03 15:04:14 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/03 15:04:14 INFO mapred.MapTask: Processing split: hdfs://ip-172-31-1-236.us-east-2.compute.internal:8020/user/danielrozental/teragen/part-m-00000:1006632960+33554432
17/10/03 15:04:14 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/03 15:04:14 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/03 15:04:14 INFO mapred.MapTask: soft limit at 83886080
17/10/03 15:04:14 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/03 15:04:14 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/03 15:04:14 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/03 15:04:14 INFO mapred.LocalJobRunner:
17/10/03 15:04:14 INFO mapred.MapTask: Starting flush of map output
17/10/03 15:04:14 INFO mapred.MapTask: Spilling map output
17/10/03 15:04:14 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/03 15:04:14 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(99488896); length = 1342173/6553600
17/10/03 15:04:14 INFO mapreduce.Job:  map 19% reduce 0%
17/10/03 15:04:15 INFO mapred.MapTask: Finished spill 0
17/10/03 15:04:15 INFO mapred.Task: Task:attempt_local662000802_0001_m_000006_0 is done. And is in the process of committing
17/10/03 15:04:15 INFO mapred.LocalJobRunner: map
17/10/03 15:04:15 INFO mapred.Task: Task 'attempt_local662000802_0001_m_000006_0' done.
17/10/03 15:04:15 INFO mapred.LocalJobRunner: Finishing task: attempt_local662000802_0001_m_000006_0
17/10/03 15:04:15 INFO mapred.LocalJobRunner: Starting task: attempt_local662000802_0001_m_000007_0
17/10/03 15:04:15 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/03 15:04:15 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/03 15:04:15 INFO mapred.MapTask: Processing split: hdfs://ip-172-31-1-236.us-east-2.compute.internal:8020/user/danielrozental/teragen/part-m-00000:973078528+33554432
17/10/03 15:04:15 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/03 15:04:15 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/03 15:04:15 INFO mapred.MapTask: soft limit at 83886080
17/10/03 15:04:15 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/03 15:04:15 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/03 15:04:15 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/03 15:04:15 INFO mapred.LocalJobRunner:
17/10/03 15:04:15 INFO mapred.MapTask: Starting flush of map output
17/10/03 15:04:15 INFO mapred.MapTask: Spilling map output
17/10/03 15:04:15 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/03 15:04:15 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(99488896); length = 1342173/6553600
17/10/03 15:04:15 INFO mapreduce.Job:  map 22% reduce 0%
17/10/03 15:04:15 INFO mapred.MapTask: Finished spill 0
17/10/03 15:04:15 INFO mapred.Task: Task:attempt_local662000802_0001_m_000007_0 is done. And is in the process of committing
17/10/03 15:04:15 INFO mapred.LocalJobRunner: map
17/10/03 15:04:15 INFO mapred.Task: Task 'attempt_local662000802_0001_m_000007_0' done.
17/10/03 15:04:15 INFO mapred.LocalJobRunner: Finishing task: attempt_local662000802_0001_m_000007_0
17/10/03 15:04:15 INFO mapred.LocalJobRunner: Starting task: attempt_local662000802_0001_m_000008_0
17/10/03 15:04:15 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/03 15:04:15 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/03 15:04:15 INFO mapred.MapTask: Processing split: hdfs://ip-172-31-1-236.us-east-2.compute.internal:8020/user/danielrozental/teragen/part-m-00000:939524096+33554432
17/10/03 15:04:16 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/03 15:04:16 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/03 15:04:16 INFO mapred.MapTask: soft limit at 83886080
17/10/03 15:04:16 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/03 15:04:16 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/03 15:04:16 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/03 15:04:16 INFO mapred.LocalJobRunner:
17/10/03 15:04:16 INFO mapred.MapTask: Starting flush of map output
17/10/03 15:04:16 INFO mapred.MapTask: Spilling map output
17/10/03 15:04:16 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/03 15:04:16 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(99488880); length = 1342177/6553600
17/10/03 15:04:16 INFO mapreduce.Job:  map 25% reduce 0%
17/10/03 15:04:16 INFO mapred.MapTask: Finished spill 0
17/10/03 15:04:16 INFO mapred.Task: Task:attempt_local662000802_0001_m_000008_0 is done. And is in the process of committing
17/10/03 15:04:16 INFO mapred.LocalJobRunner: map
17/10/03 15:04:16 INFO mapred.Task: Task 'attempt_local662000802_0001_m_000008_0' done.
17/10/03 15:04:16 INFO mapred.LocalJobRunner: Finishing task: attempt_local662000802_0001_m_000008_0
17/10/03 15:04:16 INFO mapred.LocalJobRunner: Starting task: attempt_local662000802_0001_m_000009_0
17/10/03 15:04:16 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/03 15:04:16 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/03 15:04:16 INFO mapred.MapTask: Processing split: hdfs://ip-172-31-1-236.us-east-2.compute.internal:8020/user/danielrozental/teragen/part-m-00000:905969664+33554432
17/10/03 15:04:16 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/03 15:04:16 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/03 15:04:16 INFO mapred.MapTask: soft limit at 83886080
17/10/03 15:04:16 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/03 15:04:16 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/03 15:04:16 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/03 15:04:17 INFO mapred.LocalJobRunner:
17/10/03 15:04:17 INFO mapred.MapTask: Starting flush of map output
17/10/03 15:04:17 INFO mapred.MapTask: Spilling map output
17/10/03 15:04:17 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/03 15:04:17 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(99488896); length = 1342173/6553600
17/10/03 15:04:17 INFO mapreduce.Job:  map 28% reduce 0%
17/10/03 15:04:17 INFO mapred.MapTask: Finished spill 0
17/10/03 15:04:17 INFO mapred.Task: Task:attempt_local662000802_0001_m_000009_0 is done. And is in the process of committing
17/10/03 15:04:17 INFO mapred.LocalJobRunner: map
17/10/03 15:04:17 INFO mapred.Task: Task 'attempt_local662000802_0001_m_000009_0' done.
17/10/03 15:04:17 INFO mapred.LocalJobRunner: Finishing task: attempt_local662000802_0001_m_000009_0
17/10/03 15:04:17 INFO mapred.LocalJobRunner: Starting task: attempt_local662000802_0001_m_000010_0
17/10/03 15:04:17 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/03 15:04:17 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/03 15:04:17 INFO mapred.MapTask: Processing split: hdfs://ip-172-31-1-236.us-east-2.compute.internal:8020/user/danielrozental/teragen/part-m-00000:872415232+33554432
17/10/03 15:04:17 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/03 15:04:17 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/03 15:04:17 INFO mapred.MapTask: soft limit at 83886080
17/10/03 15:04:17 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/03 15:04:17 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/03 15:04:17 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/03 15:04:18 INFO mapred.LocalJobRunner:
17/10/03 15:04:18 INFO mapred.MapTask: Starting flush of map output
17/10/03 15:04:18 INFO mapred.MapTask: Spilling map output
17/10/03 15:04:18 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/03 15:04:18 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(99488896); length = 1342173/6553600
17/10/03 15:04:18 INFO mapreduce.Job:  map 31% reduce 0%
17/10/03 15:04:18 INFO mapred.MapTask: Finished spill 0
17/10/03 15:04:18 INFO mapred.Task: Task:attempt_local662000802_0001_m_000010_0 is done. And is in the process of committing
17/10/03 15:04:18 INFO mapred.LocalJobRunner: map
17/10/03 15:04:18 INFO mapred.Task: Task 'attempt_local662000802_0001_m_000010_0' done.
17/10/03 15:04:18 INFO mapred.LocalJobRunner: Finishing task: attempt_local662000802_0001_m_000010_0
17/10/03 15:04:18 INFO mapred.LocalJobRunner: Starting task: attempt_local662000802_0001_m_000011_0
17/10/03 15:04:18 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/03 15:04:18 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/03 15:04:18 INFO mapred.MapTask: Processing split: hdfs://ip-172-31-1-236.us-east-2.compute.internal:8020/user/danielrozental/teragen/part-m-00000:838860800+33554432
17/10/03 15:04:18 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/03 15:04:18 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/03 15:04:18 INFO mapred.MapTask: soft limit at 83886080
17/10/03 15:04:18 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/03 15:04:18 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/03 15:04:18 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/03 15:04:19 INFO mapred.LocalJobRunner:
17/10/03 15:04:19 INFO mapred.MapTask: Starting flush of map output
17/10/03 15:04:19 INFO mapred.MapTask: Spilling map output
17/10/03 15:04:19 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/03 15:04:19 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(99488880); length = 1342177/6553600
17/10/03 15:04:19 INFO mapreduce.Job:  map 34% reduce 0%
17/10/03 15:04:19 INFO mapred.MapTask: Finished spill 0
17/10/03 15:04:19 INFO mapred.Task: Task:attempt_local662000802_0001_m_000011_0 is done. And is in the process of committing
17/10/03 15:04:19 INFO mapred.LocalJobRunner: map
17/10/03 15:04:19 INFO mapred.Task: Task 'attempt_local662000802_0001_m_000011_0' done.
17/10/03 15:04:19 INFO mapred.LocalJobRunner: Finishing task: attempt_local662000802_0001_m_000011_0
17/10/03 15:04:19 INFO mapred.LocalJobRunner: Starting task: attempt_local662000802_0001_m_000012_0
17/10/03 15:04:19 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/03 15:04:19 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/03 15:04:19 INFO mapred.MapTask: Processing split: hdfs://ip-172-31-1-236.us-east-2.compute.internal:8020/user/danielrozental/teragen/part-m-00000:805306368+33554432
17/10/03 15:04:19 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/03 15:04:19 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/03 15:04:19 INFO mapred.MapTask: soft limit at 83886080
17/10/03 15:04:19 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/03 15:04:19 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/03 15:04:19 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/03 15:04:20 INFO mapred.LocalJobRunner:
17/10/03 15:04:20 INFO mapred.MapTask: Starting flush of map output
17/10/03 15:04:20 INFO mapred.MapTask: Spilling map output
17/10/03 15:04:20 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/03 15:04:20 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(99488896); length = 1342173/6553600
17/10/03 15:04:20 INFO mapreduce.Job:  map 38% reduce 0%
17/10/03 15:04:20 INFO mapred.MapTask: Finished spill 0
17/10/03 15:04:20 INFO mapred.Task: Task:attempt_local662000802_0001_m_000012_0 is done. And is in the process of committing
17/10/03 15:04:20 INFO mapred.LocalJobRunner: map
17/10/03 15:04:20 INFO mapred.Task: Task 'attempt_local662000802_0001_m_000012_0' done.
17/10/03 15:04:20 INFO mapred.LocalJobRunner: Finishing task: attempt_local662000802_0001_m_000012_0
17/10/03 15:04:20 INFO mapred.LocalJobRunner: Starting task: attempt_local662000802_0001_m_000013_0
17/10/03 15:04:20 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/03 15:04:20 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/03 15:04:20 INFO mapred.MapTask: Processing split: hdfs://ip-172-31-1-236.us-east-2.compute.internal:8020/user/danielrozental/teragen/part-m-00000:771751936+33554432
17/10/03 15:04:20 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/03 15:04:20 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/03 15:04:20 INFO mapred.MapTask: soft limit at 83886080
17/10/03 15:04:20 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/03 15:04:20 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/03 15:04:20 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/03 15:04:21 INFO mapred.LocalJobRunner:
17/10/03 15:04:21 INFO mapred.MapTask: Starting flush of map output
17/10/03 15:04:21 INFO mapred.MapTask: Spilling map output
17/10/03 15:04:21 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/03 15:04:21 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(99488896); length = 1342173/6553600
17/10/03 15:04:21 INFO mapreduce.Job:  map 41% reduce 0%
17/10/03 15:04:21 INFO mapred.MapTask: Finished spill 0
17/10/03 15:04:21 INFO mapred.Task: Task:attempt_local662000802_0001_m_000013_0 is done. And is in the process of committing
17/10/03 15:04:21 INFO mapred.LocalJobRunner: map
17/10/03 15:04:21 INFO mapred.Task: Task 'attempt_local662000802_0001_m_000013_0' done.
17/10/03 15:04:21 INFO mapred.LocalJobRunner: Finishing task: attempt_local662000802_0001_m_000013_0
17/10/03 15:04:21 INFO mapred.LocalJobRunner: Starting task: attempt_local662000802_0001_m_000014_0
17/10/03 15:04:21 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/03 15:04:21 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/03 15:04:21 INFO mapred.MapTask: Processing split: hdfs://ip-172-31-1-236.us-east-2.compute.internal:8020/user/danielrozental/teragen/part-m-00000:738197504+33554432
17/10/03 15:04:21 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/03 15:04:21 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/03 15:04:21 INFO mapred.MapTask: soft limit at 83886080
17/10/03 15:04:21 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/03 15:04:21 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/03 15:04:21 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/03 15:04:22 INFO mapred.LocalJobRunner:
17/10/03 15:04:22 INFO mapred.MapTask: Starting flush of map output
17/10/03 15:04:22 INFO mapred.MapTask: Spilling map output
17/10/03 15:04:22 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/03 15:04:22 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(99488896); length = 1342173/6553600
17/10/03 15:04:22 INFO mapreduce.Job:  map 44% reduce 0%
17/10/03 15:04:22 INFO mapred.MapTask: Finished spill 0
17/10/03 15:04:22 INFO mapred.Task: Task:attempt_local662000802_0001_m_000014_0 is done. And is in the process of committing
17/10/03 15:04:22 INFO mapred.LocalJobRunner: map
17/10/03 15:04:22 INFO mapred.Task: Task 'attempt_local662000802_0001_m_000014_0' done.
17/10/03 15:04:22 INFO mapred.LocalJobRunner: Finishing task: attempt_local662000802_0001_m_000014_0
17/10/03 15:04:22 INFO mapred.LocalJobRunner: Starting task: attempt_local662000802_0001_m_000015_0
17/10/03 15:04:22 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/03 15:04:22 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/03 15:04:22 INFO mapred.MapTask: Processing split: hdfs://ip-172-31-1-236.us-east-2.compute.internal:8020/user/danielrozental/teragen/part-m-00000:704643072+33554432
17/10/03 15:04:22 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/03 15:04:22 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/03 15:04:22 INFO mapred.MapTask: soft limit at 83886080
17/10/03 15:04:22 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/03 15:04:22 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/03 15:04:22 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/03 15:04:22 INFO mapred.LocalJobRunner:
17/10/03 15:04:22 INFO mapred.MapTask: Starting flush of map output
17/10/03 15:04:22 INFO mapred.MapTask: Spilling map output
17/10/03 15:04:22 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/03 15:04:22 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(99488880); length = 1342177/6553600
17/10/03 15:04:23 INFO mapreduce.Job:  map 47% reduce 0%
17/10/03 15:04:23 INFO mapred.MapTask: Finished spill 0
17/10/03 15:04:23 INFO mapred.Task: Task:attempt_local662000802_0001_m_000015_0 is done. And is in the process of committing
17/10/03 15:04:23 INFO mapred.LocalJobRunner: map
17/10/03 15:04:23 INFO mapred.Task: Task 'attempt_local662000802_0001_m_000015_0' done.
17/10/03 15:04:23 INFO mapred.LocalJobRunner: Finishing task: attempt_local662000802_0001_m_000015_0
17/10/03 15:04:23 INFO mapred.LocalJobRunner: Starting task: attempt_local662000802_0001_m_000016_0
17/10/03 15:04:23 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/03 15:04:23 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/03 15:04:23 INFO mapred.MapTask: Processing split: hdfs://ip-172-31-1-236.us-east-2.compute.internal:8020/user/danielrozental/teragen/part-m-00000:671088640+33554432
17/10/03 15:04:23 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/03 15:04:23 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/03 15:04:23 INFO mapred.MapTask: soft limit at 83886080
17/10/03 15:04:23 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/03 15:04:23 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/03 15:04:23 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/03 15:04:23 INFO mapred.LocalJobRunner:
17/10/03 15:04:23 INFO mapred.MapTask: Starting flush of map output
17/10/03 15:04:23 INFO mapred.MapTask: Spilling map output
17/10/03 15:04:23 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/03 15:04:23 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(99488896); length = 1342173/6553600
17/10/03 15:04:24 INFO mapreduce.Job:  map 50% reduce 0%
17/10/03 15:04:24 INFO mapred.MapTask: Finished spill 0
17/10/03 15:04:24 INFO mapred.Task: Task:attempt_local662000802_0001_m_000016_0 is done. And is in the process of committing
17/10/03 15:04:24 INFO mapred.LocalJobRunner: map
17/10/03 15:04:24 INFO mapred.Task: Task 'attempt_local662000802_0001_m_000016_0' done.
17/10/03 15:04:24 INFO mapred.LocalJobRunner: Finishing task: attempt_local662000802_0001_m_000016_0
17/10/03 15:04:24 INFO mapred.LocalJobRunner: Starting task: attempt_local662000802_0001_m_000017_0
17/10/03 15:04:24 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/03 15:04:24 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/03 15:04:24 INFO mapred.MapTask: Processing split: hdfs://ip-172-31-1-236.us-east-2.compute.internal:8020/user/danielrozental/teragen/part-m-00000:637534208+33554432
17/10/03 15:04:24 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/03 15:04:24 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/03 15:04:24 INFO mapred.MapTask: soft limit at 83886080
17/10/03 15:04:24 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/03 15:04:24 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/03 15:04:24 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/03 15:04:24 INFO mapred.LocalJobRunner:
17/10/03 15:04:24 INFO mapred.MapTask: Starting flush of map output
17/10/03 15:04:24 INFO mapred.MapTask: Spilling map output
17/10/03 15:04:24 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/03 15:04:24 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(99488896); length = 1342173/6553600
17/10/03 15:04:25 INFO mapreduce.Job:  map 53% reduce 0%
17/10/03 15:04:25 INFO mapred.MapTask: Finished spill 0
17/10/03 15:04:25 INFO mapred.Task: Task:attempt_local662000802_0001_m_000017_0 is done. And is in the process of committing
17/10/03 15:04:25 INFO mapred.LocalJobRunner: map
17/10/03 15:04:25 INFO mapred.Task: Task 'attempt_local662000802_0001_m_000017_0' done.
17/10/03 15:04:25 INFO mapred.LocalJobRunner: Finishing task: attempt_local662000802_0001_m_000017_0
17/10/03 15:04:25 INFO mapred.LocalJobRunner: Starting task: attempt_local662000802_0001_m_000018_0
17/10/03 15:04:25 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/03 15:04:25 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/03 15:04:25 INFO mapred.MapTask: Processing split: hdfs://ip-172-31-1-236.us-east-2.compute.internal:8020/user/danielrozental/teragen/part-m-00000:603979776+33554432
17/10/03 15:04:25 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/03 15:04:25 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/03 15:04:25 INFO mapred.MapTask: soft limit at 83886080
17/10/03 15:04:25 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/03 15:04:25 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/03 15:04:25 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/03 15:04:25 INFO mapred.LocalJobRunner:
17/10/03 15:04:25 INFO mapred.MapTask: Starting flush of map output
17/10/03 15:04:25 INFO mapred.MapTask: Spilling map output
17/10/03 15:04:25 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/03 15:04:25 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(99488880); length = 1342177/6553600
17/10/03 15:04:26 INFO mapred.MapTask: Finished spill 0
17/10/03 15:04:26 INFO mapred.Task: Task:attempt_local662000802_0001_m_000018_0 is done. And is in the process of committing
17/10/03 15:04:26 INFO mapred.LocalJobRunner: map
17/10/03 15:04:26 INFO mapred.Task: Task 'attempt_local662000802_0001_m_000018_0' done.
17/10/03 15:04:26 INFO mapred.LocalJobRunner: Finishing task: attempt_local662000802_0001_m_000018_0
17/10/03 15:04:26 INFO mapred.LocalJobRunner: Starting task: attempt_local662000802_0001_m_000019_0
17/10/03 15:04:26 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/03 15:04:26 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/03 15:04:26 INFO mapred.MapTask: Processing split: hdfs://ip-172-31-1-236.us-east-2.compute.internal:8020/user/danielrozental/teragen/part-m-00000:570425344+33554432
17/10/03 15:04:26 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/03 15:04:26 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/03 15:04:26 INFO mapred.MapTask: soft limit at 83886080
17/10/03 15:04:26 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/03 15:04:26 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/03 15:04:26 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/03 15:04:26 INFO mapreduce.Job:  map 100% reduce 0%
17/10/03 15:04:26 INFO mapred.LocalJobRunner:
17/10/03 15:04:26 INFO mapred.MapTask: Starting flush of map output
17/10/03 15:04:26 INFO mapred.MapTask: Spilling map output
17/10/03 15:04:26 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/03 15:04:26 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(99488896); length = 1342173/6553600
17/10/03 15:04:27 INFO mapred.MapTask: Finished spill 0
17/10/03 15:04:27 INFO mapred.Task: Task:attempt_local662000802_0001_m_000019_0 is done. And is in the process of committing
17/10/03 15:04:27 INFO mapred.LocalJobRunner: map
17/10/03 15:04:27 INFO mapred.Task: Task 'attempt_local662000802_0001_m_000019_0' done.
17/10/03 15:04:27 INFO mapred.LocalJobRunner: Finishing task: attempt_local662000802_0001_m_000019_0
17/10/03 15:04:27 INFO mapred.LocalJobRunner: Starting task: attempt_local662000802_0001_m_000020_0
17/10/03 15:04:27 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/03 15:04:27 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/03 15:04:27 INFO mapred.MapTask: Processing split: hdfs://ip-172-31-1-236.us-east-2.compute.internal:8020/user/danielrozental/teragen/part-m-00000:536870912+33554432
17/10/03 15:04:27 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/03 15:04:27 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/03 15:04:27 INFO mapred.MapTask: soft limit at 83886080
17/10/03 15:04:27 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/03 15:04:27 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/03 15:04:27 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/03 15:04:27 INFO mapred.LocalJobRunner:
17/10/03 15:04:27 INFO mapred.MapTask: Starting flush of map output
17/10/03 15:04:27 INFO mapred.MapTask: Spilling map output
17/10/03 15:04:27 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/03 15:04:27 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(99488896); length = 1342173/6553600
17/10/03 15:04:28 INFO mapred.MapTask: Finished spill 0
17/10/03 15:04:28 INFO mapred.Task: Task:attempt_local662000802_0001_m_000020_0 is done. And is in the process of committing
17/10/03 15:04:28 INFO mapred.LocalJobRunner: map
17/10/03 15:04:28 INFO mapred.Task: Task 'attempt_local662000802_0001_m_000020_0' done.
17/10/03 15:04:28 INFO mapred.LocalJobRunner: Finishing task: attempt_local662000802_0001_m_000020_0
17/10/03 15:04:28 INFO mapred.LocalJobRunner: Starting task: attempt_local662000802_0001_m_000021_0
17/10/03 15:04:28 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/03 15:04:28 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/03 15:04:28 INFO mapred.MapTask: Processing split: hdfs://ip-172-31-1-236.us-east-2.compute.internal:8020/user/danielrozental/teragen/part-m-00000:503316480+33554432
17/10/03 15:04:28 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/03 15:04:28 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/03 15:04:28 INFO mapred.MapTask: soft limit at 83886080
17/10/03 15:04:28 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/03 15:04:28 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/03 15:04:28 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/03 15:04:28 INFO mapred.LocalJobRunner:
17/10/03 15:04:28 INFO mapred.MapTask: Starting flush of map output
17/10/03 15:04:28 INFO mapred.MapTask: Spilling map output
17/10/03 15:04:28 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/03 15:04:28 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(99488880); length = 1342177/6553600
17/10/03 15:04:29 INFO mapred.MapTask: Finished spill 0
17/10/03 15:04:29 INFO mapred.Task: Task:attempt_local662000802_0001_m_000021_0 is done. And is in the process of committing
17/10/03 15:04:29 INFO mapred.LocalJobRunner: map
17/10/03 15:04:29 INFO mapred.Task: Task 'attempt_local662000802_0001_m_000021_0' done.
17/10/03 15:04:29 INFO mapred.LocalJobRunner: Finishing task: attempt_local662000802_0001_m_000021_0
17/10/03 15:04:29 INFO mapred.LocalJobRunner: Starting task: attempt_local662000802_0001_m_000022_0
17/10/03 15:04:29 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/03 15:04:29 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/03 15:04:29 INFO mapred.MapTask: Processing split: hdfs://ip-172-31-1-236.us-east-2.compute.internal:8020/user/danielrozental/teragen/part-m-00000:469762048+33554432
17/10/03 15:04:29 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/03 15:04:29 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/03 15:04:29 INFO mapred.MapTask: soft limit at 83886080
17/10/03 15:04:29 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/03 15:04:29 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/03 15:04:29 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/03 15:04:29 INFO mapred.LocalJobRunner:
17/10/03 15:04:29 INFO mapred.MapTask: Starting flush of map output
17/10/03 15:04:29 INFO mapred.MapTask: Spilling map output
17/10/03 15:04:29 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/03 15:04:29 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(99488896); length = 1342173/6553600
17/10/03 15:04:30 INFO mapred.MapTask: Finished spill 0
17/10/03 15:04:30 INFO mapred.Task: Task:attempt_local662000802_0001_m_000022_0 is done. And is in the process of committing
17/10/03 15:04:30 INFO mapred.LocalJobRunner: map
17/10/03 15:04:30 INFO mapred.Task: Task 'attempt_local662000802_0001_m_000022_0' done.
17/10/03 15:04:30 INFO mapred.LocalJobRunner: Finishing task: attempt_local662000802_0001_m_000022_0
17/10/03 15:04:30 INFO mapred.LocalJobRunner: Starting task: attempt_local662000802_0001_m_000023_0
17/10/03 15:04:30 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/03 15:04:30 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/03 15:04:30 INFO mapred.MapTask: Processing split: hdfs://ip-172-31-1-236.us-east-2.compute.internal:8020/user/danielrozental/teragen/part-m-00000:436207616+33554432
17/10/03 15:04:30 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/03 15:04:30 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/03 15:04:30 INFO mapred.MapTask: soft limit at 83886080
17/10/03 15:04:30 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/03 15:04:30 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/03 15:04:30 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/03 15:04:30 INFO mapred.LocalJobRunner:
17/10/03 15:04:30 INFO mapred.MapTask: Starting flush of map output
17/10/03 15:04:30 INFO mapred.MapTask: Spilling map output
17/10/03 15:04:30 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/03 15:04:30 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(99488896); length = 1342173/6553600
17/10/03 15:04:31 INFO mapred.MapTask: Finished spill 0
17/10/03 15:04:31 INFO mapred.Task: Task:attempt_local662000802_0001_m_000023_0 is done. And is in the process of committing
17/10/03 15:04:31 INFO mapred.LocalJobRunner: map
17/10/03 15:04:31 INFO mapred.Task: Task 'attempt_local662000802_0001_m_000023_0' done.
17/10/03 15:04:31 INFO mapred.LocalJobRunner: Finishing task: attempt_local662000802_0001_m_000023_0
17/10/03 15:04:31 INFO mapred.LocalJobRunner: Starting task: attempt_local662000802_0001_m_000024_0
17/10/03 15:04:31 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/03 15:04:31 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/03 15:04:31 INFO mapred.MapTask: Processing split: hdfs://ip-172-31-1-236.us-east-2.compute.internal:8020/user/danielrozental/teragen/part-m-00000:402653184+33554432
17/10/03 15:04:31 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/03 15:04:31 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/03 15:04:31 INFO mapred.MapTask: soft limit at 83886080
17/10/03 15:04:31 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/03 15:04:31 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/03 15:04:31 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/03 15:04:31 INFO mapred.LocalJobRunner:
17/10/03 15:04:31 INFO mapred.MapTask: Starting flush of map output
17/10/03 15:04:31 INFO mapred.MapTask: Spilling map output
17/10/03 15:04:31 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/03 15:04:31 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(99488880); length = 1342177/6553600
17/10/03 15:04:31 INFO mapreduce.Job:  map 75% reduce 0%
17/10/03 15:04:32 INFO mapred.MapTask: Finished spill 0
17/10/03 15:04:32 INFO mapred.Task: Task:attempt_local662000802_0001_m_000024_0 is done. And is in the process of committing
17/10/03 15:04:32 INFO mapred.LocalJobRunner: map
17/10/03 15:04:32 INFO mapred.Task: Task 'attempt_local662000802_0001_m_000024_0' done.
17/10/03 15:04:32 INFO mapred.LocalJobRunner: Finishing task: attempt_local662000802_0001_m_000024_0
17/10/03 15:04:32 INFO mapred.LocalJobRunner: Starting task: attempt_local662000802_0001_m_000025_0
17/10/03 15:04:32 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/03 15:04:32 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/03 15:04:32 INFO mapred.MapTask: Processing split: hdfs://ip-172-31-1-236.us-east-2.compute.internal:8020/user/danielrozental/teragen/part-m-00000:369098752+33554432
17/10/03 15:04:32 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/03 15:04:32 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/03 15:04:32 INFO mapred.MapTask: soft limit at 83886080
17/10/03 15:04:32 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/03 15:04:32 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/03 15:04:32 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/03 15:04:32 INFO mapred.LocalJobRunner:
17/10/03 15:04:32 INFO mapred.MapTask: Starting flush of map output
17/10/03 15:04:32 INFO mapred.MapTask: Spilling map output
17/10/03 15:04:32 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/03 15:04:32 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(99488896); length = 1342173/6553600
17/10/03 15:04:32 INFO mapreduce.Job:  map 78% reduce 0%
17/10/03 15:04:33 INFO mapred.MapTask: Finished spill 0
17/10/03 15:04:33 INFO mapred.Task: Task:attempt_local662000802_0001_m_000025_0 is done. And is in the process of committing
17/10/03 15:04:33 INFO mapred.LocalJobRunner: map
17/10/03 15:04:33 INFO mapred.Task: Task 'attempt_local662000802_0001_m_000025_0' done.
17/10/03 15:04:33 INFO mapred.LocalJobRunner: Finishing task: attempt_local662000802_0001_m_000025_0
17/10/03 15:04:33 INFO mapred.LocalJobRunner: Starting task: attempt_local662000802_0001_m_000026_0
17/10/03 15:04:33 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/03 15:04:33 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/03 15:04:33 INFO mapred.MapTask: Processing split: hdfs://ip-172-31-1-236.us-east-2.compute.internal:8020/user/danielrozental/teragen/part-m-00000:335544320+33554432
17/10/03 15:04:33 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/03 15:04:33 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/03 15:04:33 INFO mapred.MapTask: soft limit at 83886080
17/10/03 15:04:33 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/03 15:04:33 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/03 15:04:33 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/03 15:04:33 INFO mapred.LocalJobRunner:
17/10/03 15:04:33 INFO mapred.MapTask: Starting flush of map output
17/10/03 15:04:33 INFO mapred.MapTask: Spilling map output
17/10/03 15:04:33 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/03 15:04:33 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(99488896); length = 1342173/6553600
17/10/03 15:04:33 INFO mapreduce.Job:  map 81% reduce 0%
17/10/03 15:04:33 INFO mapred.MapTask: Finished spill 0
17/10/03 15:04:33 INFO mapred.Task: Task:attempt_local662000802_0001_m_000026_0 is done. And is in the process of committing
17/10/03 15:04:33 INFO mapred.LocalJobRunner: map
17/10/03 15:04:33 INFO mapred.Task: Task 'attempt_local662000802_0001_m_000026_0' done.
17/10/03 15:04:33 INFO mapred.LocalJobRunner: Finishing task: attempt_local662000802_0001_m_000026_0
17/10/03 15:04:33 INFO mapred.LocalJobRunner: Starting task: attempt_local662000802_0001_m_000027_0
17/10/03 15:04:33 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/03 15:04:33 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/03 15:04:33 INFO mapred.MapTask: Processing split: hdfs://ip-172-31-1-236.us-east-2.compute.internal:8020/user/danielrozental/teragen/part-m-00000:301989888+33554432
17/10/03 15:04:34 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/03 15:04:34 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/03 15:04:34 INFO mapred.MapTask: soft limit at 83886080
17/10/03 15:04:34 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/03 15:04:34 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/03 15:04:34 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/03 15:04:34 INFO mapred.LocalJobRunner:
17/10/03 15:04:34 INFO mapred.MapTask: Starting flush of map output
17/10/03 15:04:34 INFO mapred.MapTask: Spilling map output
17/10/03 15:04:34 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/03 15:04:34 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(99488880); length = 1342177/6553600
17/10/03 15:04:34 INFO mapreduce.Job:  map 84% reduce 0%
17/10/03 15:04:34 INFO mapred.MapTask: Finished spill 0
17/10/03 15:04:34 INFO mapred.Task: Task:attempt_local662000802_0001_m_000027_0 is done. And is in the process of committing
17/10/03 15:04:34 INFO mapred.LocalJobRunner: map
17/10/03 15:04:34 INFO mapred.Task: Task 'attempt_local662000802_0001_m_000027_0' done.
17/10/03 15:04:34 INFO mapred.LocalJobRunner: Finishing task: attempt_local662000802_0001_m_000027_0
17/10/03 15:04:34 INFO mapred.LocalJobRunner: Starting task: attempt_local662000802_0001_m_000028_0
17/10/03 15:04:34 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/03 15:04:34 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/03 15:04:34 INFO mapred.MapTask: Processing split: hdfs://ip-172-31-1-236.us-east-2.compute.internal:8020/user/danielrozental/teragen/part-m-00000:268435456+33554432
17/10/03 15:04:34 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/03 15:04:34 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/03 15:04:34 INFO mapred.MapTask: soft limit at 83886080
17/10/03 15:04:34 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/03 15:04:34 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/03 15:04:34 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/03 15:04:35 INFO mapred.LocalJobRunner:
17/10/03 15:04:35 INFO mapred.MapTask: Starting flush of map output
17/10/03 15:04:35 INFO mapred.MapTask: Spilling map output
17/10/03 15:04:35 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/03 15:04:35 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(99488896); length = 1342173/6553600
17/10/03 15:04:35 INFO mapreduce.Job:  map 88% reduce 0%
17/10/03 15:04:35 INFO mapred.MapTask: Finished spill 0
17/10/03 15:04:35 INFO mapred.Task: Task:attempt_local662000802_0001_m_000028_0 is done. And is in the process of committing
17/10/03 15:04:35 INFO mapred.LocalJobRunner: map
17/10/03 15:04:35 INFO mapred.Task: Task 'attempt_local662000802_0001_m_000028_0' done.
17/10/03 15:04:35 INFO mapred.LocalJobRunner: Finishing task: attempt_local662000802_0001_m_000028_0
17/10/03 15:04:35 INFO mapred.LocalJobRunner: Starting task: attempt_local662000802_0001_m_000029_0
17/10/03 15:04:35 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/03 15:04:35 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/03 15:04:35 INFO mapred.MapTask: Processing split: hdfs://ip-172-31-1-236.us-east-2.compute.internal:8020/user/danielrozental/teragen/part-m-00000:234881024+33554432
17/10/03 15:04:35 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/03 15:04:35 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/03 15:04:35 INFO mapred.MapTask: soft limit at 83886080
17/10/03 15:04:35 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/03 15:04:35 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/03 15:04:35 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/03 15:04:36 INFO mapred.LocalJobRunner:
17/10/03 15:04:36 INFO mapred.MapTask: Starting flush of map output
17/10/03 15:04:36 INFO mapred.MapTask: Spilling map output
17/10/03 15:04:36 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/03 15:04:36 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(99488896); length = 1342173/6553600
17/10/03 15:04:36 INFO mapreduce.Job:  map 91% reduce 0%
17/10/03 15:04:36 INFO mapred.MapTask: Finished spill 0
17/10/03 15:04:36 INFO mapred.Task: Task:attempt_local662000802_0001_m_000029_0 is done. And is in the process of committing
17/10/03 15:04:36 INFO mapred.LocalJobRunner: map
17/10/03 15:04:36 INFO mapred.Task: Task 'attempt_local662000802_0001_m_000029_0' done.
17/10/03 15:04:36 INFO mapred.LocalJobRunner: Finishing task: attempt_local662000802_0001_m_000029_0
17/10/03 15:04:36 INFO mapred.LocalJobRunner: Starting task: attempt_local662000802_0001_m_000030_0
17/10/03 15:04:36 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/03 15:04:36 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/03 15:04:36 INFO mapred.MapTask: Processing split: hdfs://ip-172-31-1-236.us-east-2.compute.internal:8020/user/danielrozental/teragen/part-m-00000:201326592+33554432
17/10/03 15:04:36 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/03 15:04:36 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/03 15:04:36 INFO mapred.MapTask: soft limit at 83886080
17/10/03 15:04:36 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/03 15:04:36 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/03 15:04:36 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/03 15:04:37 INFO mapred.LocalJobRunner:
17/10/03 15:04:37 INFO mapred.MapTask: Starting flush of map output
17/10/03 15:04:37 INFO mapred.MapTask: Spilling map output
17/10/03 15:04:37 INFO mapred.MapTask: bufstart = 0; bufend = 34225590; bufvoid = 104857600
17/10/03 15:04:37 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872220(99488880); length = 1342177/6553600
17/10/03 15:04:37 INFO mapreduce.Job:  map 94% reduce 0%
17/10/03 15:04:37 INFO mapred.MapTask: Finished spill 0
17/10/03 15:04:37 INFO mapred.Task: Task:attempt_local662000802_0001_m_000030_0 is done. And is in the process of committing
17/10/03 15:04:37 INFO mapred.LocalJobRunner: map
17/10/03 15:04:37 INFO mapred.Task: Task 'attempt_local662000802_0001_m_000030_0' done.
17/10/03 15:04:37 INFO mapred.LocalJobRunner: Finishing task: attempt_local662000802_0001_m_000030_0
17/10/03 15:04:37 INFO mapred.LocalJobRunner: Starting task: attempt_local662000802_0001_m_000031_0
17/10/03 15:04:37 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/03 15:04:37 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/03 15:04:37 INFO mapred.MapTask: Processing split: hdfs://ip-172-31-1-236.us-east-2.compute.internal:8020/user/danielrozental/teragen/part-m-00000:1040187392+33554408
17/10/03 15:04:37 INFO mapred.MapTask: (EQUATOR) 0 kvi 26214396(104857584)
17/10/03 15:04:37 INFO mapred.MapTask: mapreduce.task.io.sort.mb: 100
17/10/03 15:04:37 INFO mapred.MapTask: soft limit at 83886080
17/10/03 15:04:37 INFO mapred.MapTask: bufstart = 0; bufvoid = 104857600
17/10/03 15:04:37 INFO mapred.MapTask: kvstart = 26214396; length = 6553600
17/10/03 15:04:37 INFO mapred.MapTask: Map output collector class = org.apache.hadoop.mapred.MapTask$MapOutputBuffer
17/10/03 15:04:37 INFO mapred.LocalJobRunner:
17/10/03 15:04:37 INFO mapred.MapTask: Starting flush of map output
17/10/03 15:04:37 INFO mapred.MapTask: Spilling map output
17/10/03 15:04:37 INFO mapred.MapTask: bufstart = 0; bufend = 34225488; bufvoid = 104857600
17/10/03 15:04:37 INFO mapred.MapTask: kvstart = 26214396(104857584); kvend = 24872224(99488896); length = 1342173/6553600
17/10/03 15:04:38 INFO mapreduce.Job:  map 97% reduce 0%
17/10/03 15:04:38 INFO mapred.MapTask: Finished spill 0
17/10/03 15:04:38 INFO mapred.Task: Task:attempt_local662000802_0001_m_000031_0 is done. And is in the process of committing
17/10/03 15:04:38 INFO mapred.LocalJobRunner: map
17/10/03 15:04:38 INFO mapred.Task: Task 'attempt_local662000802_0001_m_000031_0' done.
17/10/03 15:04:38 INFO mapred.LocalJobRunner: Finishing task: attempt_local662000802_0001_m_000031_0
17/10/03 15:04:38 INFO mapred.LocalJobRunner: map task executor complete.
17/10/03 15:04:38 INFO mapred.LocalJobRunner: Waiting for reduce tasks
17/10/03 15:04:38 INFO mapred.LocalJobRunner: Starting task: attempt_local662000802_0001_r_000000_0
17/10/03 15:04:38 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/03 15:04:38 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/03 15:04:38 INFO mapred.ReduceTask: Using ShuffleConsumerPlugin: org.apache.hadoop.mapreduce.task.reduce.Shuffle@698114b1
17/10/03 15:04:38 INFO reduce.MergeManagerImpl: MergerManager: memoryLimit=187537808, maxSingleShuffleLimit=46884452, mergeThreshold=123774960, ioSortFactor=10, memToMemMergeOutputsThreshold=10
17/10/03 15:04:38 INFO reduce.EventFetcher: attempt_local662000802_0001_r_000000_0 Thread started: EventFetcher for fetching Map Completion Events
17/10/03 15:04:38 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local662000802_0001_m_000026_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/03 15:04:38 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local662000802_0001_m_000026_0
17/10/03 15:04:38 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 1, commitMemory -> 0, usedMemory ->34896578
17/10/03 15:04:38 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local662000802_0001_m_000002_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/03 15:04:38 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local662000802_0001_m_000002_0
17/10/03 15:04:38 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 2, commitMemory -> 34896578, usedMemory ->69793156
17/10/03 15:04:38 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local662000802_0001_m_000015_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/03 15:04:38 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local662000802_0001_m_000015_0
17/10/03 15:04:38 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 3, commitMemory -> 69793156, usedMemory ->104689838
17/10/03 15:04:39 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local662000802_0001_m_000014_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/03 15:04:39 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local662000802_0001_m_000014_0
17/10/03 15:04:39 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 4, commitMemory -> 104689838, usedMemory ->139586416
17/10/03 15:04:39 INFO reduce.MergeManagerImpl: Starting inMemoryMerger's merge since commitMemory=139586416 > mergeThreshold=123774960. Current usedMemory=139586416
17/10/03 15:04:39 INFO reduce.MergeThread: InMemoryMerger - Thread to merge in-memory shuffled map-outputs: Starting merge with 4 segments, while ignoring 0 segments
17/10/03 15:04:39 INFO reduce.MergeManagerImpl: Initiating in-memory merge with 4 segments...
17/10/03 15:04:39 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local662000802_0001_m_000000_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/03 15:04:39 INFO mapred.Merger: Merging 4 sorted segments
17/10/03 15:04:39 INFO mapred.Merger: Down to the last merge-pass, with 4 segments left of total size: 139586364 bytes
17/10/03 15:04:39 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local662000802_0001_m_000000_0
17/10/03 15:04:39 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 1, commitMemory -> 0, usedMemory ->174483098
17/10/03 15:04:39 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local662000802_0001_m_000027_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/03 15:04:39 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local662000802_0001_m_000027_0
17/10/03 15:04:39 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 2, commitMemory -> 34896682, usedMemory ->209379780
17/10/03 15:04:39 INFO reduce.LocalFetcher: fetcher#1 - MergeManager returned Status.WAIT ...
17/10/03 15:04:39 INFO mapreduce.Job:  map 100% reduce 0%
17/10/03 15:04:40 INFO reduce.MergeManagerImpl: attempt_local662000802_0001_r_000000_0 Merge of the 4 files in-memory complete. Local file is /tmp/hadoop-danielrozental/mapred/local/localRunner/danielrozental/jobcache/job_local662000802_0001/attempt_local662000802_0001_r_000000_0/output/map_26.out.merged of size 139586414
17/10/03 15:04:40 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local662000802_0001_m_000013_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/03 15:04:40 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local662000802_0001_m_000013_0
17/10/03 15:04:40 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 3, commitMemory -> 69793364, usedMemory ->104689942
17/10/03 15:04:40 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local662000802_0001_m_000001_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/03 15:04:40 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local662000802_0001_m_000001_0
17/10/03 15:04:40 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 4, commitMemory -> 104689942, usedMemory ->139586520
17/10/03 15:04:40 INFO reduce.MergeManagerImpl: Starting inMemoryMerger's merge since commitMemory=139586520 > mergeThreshold=123774960. Current usedMemory=139586520
17/10/03 15:04:40 INFO reduce.MergeThread: InMemoryMerger - Thread to merge in-memory shuffled map-outputs: Starting merge with 4 segments, while ignoring 0 segments
17/10/03 15:04:40 INFO reduce.MergeManagerImpl: Initiating in-memory merge with 4 segments...
17/10/03 15:04:40 INFO mapred.Merger: Merging 4 sorted segments
17/10/03 15:04:40 INFO mapred.Merger: Down to the last merge-pass, with 4 segments left of total size: 139586468 bytes
17/10/03 15:04:40 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local662000802_0001_m_000028_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/03 15:04:40 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local662000802_0001_m_000028_0
17/10/03 15:04:40 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 1, commitMemory -> 0, usedMemory ->174483098
17/10/03 15:04:40 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local662000802_0001_m_000029_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/03 15:04:40 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local662000802_0001_m_000029_0
17/10/03 15:04:40 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 2, commitMemory -> 34896578, usedMemory ->209379676
17/10/03 15:04:40 INFO reduce.LocalFetcher: fetcher#1 - MergeManager returned Status.WAIT ...
17/10/03 15:04:41 INFO reduce.MergeManagerImpl: attempt_local662000802_0001_r_000000_0 Merge of the 4 files in-memory complete. Local file is /tmp/hadoop-danielrozental/mapred/local/localRunner/danielrozental/jobcache/job_local662000802_0001/attempt_local662000802_0001_r_000000_0/output/map_13.out.merged of size 139586518
17/10/03 15:04:41 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local662000802_0001_m_000005_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/03 15:04:41 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local662000802_0001_m_000005_0
17/10/03 15:04:41 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 3, commitMemory -> 69793156, usedMemory ->104689734
17/10/03 15:04:41 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local662000802_0001_m_000006_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/03 15:04:41 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local662000802_0001_m_000006_0
17/10/03 15:04:41 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 4, commitMemory -> 104689734, usedMemory ->139586312
17/10/03 15:04:41 INFO reduce.MergeManagerImpl: Starting inMemoryMerger's merge since commitMemory=139586312 > mergeThreshold=123774960. Current usedMemory=139586312
17/10/03 15:04:41 INFO reduce.MergeThread: InMemoryMerger - Thread to merge in-memory shuffled map-outputs: Starting merge with 4 segments, while ignoring 0 segments
17/10/03 15:04:41 INFO reduce.MergeManagerImpl: Initiating in-memory merge with 4 segments...
17/10/03 15:04:41 INFO mapred.Merger: Merging 4 sorted segments
17/10/03 15:04:41 INFO mapred.Merger: Down to the last merge-pass, with 4 segments left of total size: 139586260 bytes
17/10/03 15:04:41 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local662000802_0001_m_000018_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/03 15:04:41 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local662000802_0001_m_000018_0
17/10/03 15:04:41 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 1, commitMemory -> 0, usedMemory ->174482994
17/10/03 15:04:41 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local662000802_0001_m_000030_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/03 15:04:41 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local662000802_0001_m_000030_0
17/10/03 15:04:41 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 2, commitMemory -> 34896682, usedMemory ->209379676
17/10/03 15:04:41 INFO reduce.LocalFetcher: fetcher#1 - MergeManager returned Status.WAIT ...
17/10/03 15:04:42 INFO reduce.MergeManagerImpl: attempt_local662000802_0001_r_000000_0 Merge of the 4 files in-memory complete. Local file is /tmp/hadoop-danielrozental/mapred/local/localRunner/danielrozental/jobcache/job_local662000802_0001/attempt_local662000802_0001_r_000000_0/output/map_28.out.merged of size 139586310
17/10/03 15:04:42 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local662000802_0001_m_000017_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/03 15:04:42 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local662000802_0001_m_000017_0
17/10/03 15:04:42 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 3, commitMemory -> 69793364, usedMemory ->104689942
17/10/03 15:04:42 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local662000802_0001_m_000003_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/03 15:04:42 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local662000802_0001_m_000003_0
17/10/03 15:04:42 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 4, commitMemory -> 104689942, usedMemory ->139586624
17/10/03 15:04:42 INFO reduce.MergeManagerImpl: Starting inMemoryMerger's merge since commitMemory=139586624 > mergeThreshold=123774960. Current usedMemory=139586624
17/10/03 15:04:42 INFO reduce.MergeThread: InMemoryMerger - Thread to merge in-memory shuffled map-outputs: Starting merge with 4 segments, while ignoring 0 segments
17/10/03 15:04:42 INFO reduce.MergeManagerImpl: Initiating in-memory merge with 4 segments...
17/10/03 15:04:42 INFO mapred.Merger: Merging 4 sorted segments
17/10/03 15:04:42 INFO mapred.Merger: Down to the last merge-pass, with 4 segments left of total size: 139586572 bytes
17/10/03 15:04:42 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local662000802_0001_m_000031_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/03 15:04:42 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local662000802_0001_m_000031_0
17/10/03 15:04:42 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 1, commitMemory -> 0, usedMemory ->174483202
17/10/03 15:04:42 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local662000802_0001_m_000004_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/03 15:04:42 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local662000802_0001_m_000004_0
17/10/03 15:04:42 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 2, commitMemory -> 34896578, usedMemory ->209379780
17/10/03 15:04:42 INFO reduce.LocalFetcher: fetcher#1 - MergeManager returned Status.WAIT ...
17/10/03 15:04:43 INFO reduce.MergeManagerImpl: attempt_local662000802_0001_r_000000_0 Merge of the 4 files in-memory complete. Local file is /tmp/hadoop-danielrozental/mapred/local/localRunner/danielrozental/jobcache/job_local662000802_0001/attempt_local662000802_0001_r_000000_0/output/map_17.out.merged of size 139586622
17/10/03 15:04:43 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local662000802_0001_m_000016_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/03 15:04:43 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local662000802_0001_m_000016_0
17/10/03 15:04:43 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 3, commitMemory -> 69793156, usedMemory ->104689734
17/10/03 15:04:43 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local662000802_0001_m_000008_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/03 15:04:43 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local662000802_0001_m_000008_0
17/10/03 15:04:43 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 4, commitMemory -> 104689734, usedMemory ->139586416
17/10/03 15:04:43 INFO reduce.MergeManagerImpl: Starting inMemoryMerger's merge since commitMemory=139586416 > mergeThreshold=123774960. Current usedMemory=139586416
17/10/03 15:04:43 INFO reduce.MergeThread: InMemoryMerger - Thread to merge in-memory shuffled map-outputs: Starting merge with 4 segments, while ignoring 0 segments
17/10/03 15:04:43 INFO reduce.MergeManagerImpl: Initiating in-memory merge with 4 segments...
17/10/03 15:04:43 INFO mapred.Merger: Merging 4 sorted segments
17/10/03 15:04:43 INFO mapred.Merger: Down to the last merge-pass, with 4 segments left of total size: 139586364 bytes
17/10/03 15:04:43 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local662000802_0001_m_000022_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/03 15:04:43 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local662000802_0001_m_000022_0
17/10/03 15:04:43 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 1, commitMemory -> 0, usedMemory ->174482994
17/10/03 15:04:44 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local662000802_0001_m_000009_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/03 15:04:44 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local662000802_0001_m_000009_0
17/10/03 15:04:44 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 2, commitMemory -> 34896578, usedMemory ->209379572
17/10/03 15:04:44 INFO reduce.LocalFetcher: fetcher#1 - MergeManager returned Status.WAIT ...
17/10/03 15:04:44 INFO mapred.LocalJobRunner: reduce > copy task(attempt_local662000802_0001_m_000009_0 succeeded at 33279.98 MB/s) Aggregated copy rate(22 of 32 at 732160.12 MB/s)
17/10/03 15:04:44 INFO reduce.MergeManagerImpl: attempt_local662000802_0001_r_000000_0 Merge of the 4 files in-memory complete. Local file is /tmp/hadoop-danielrozental/mapred/local/localRunner/danielrozental/jobcache/job_local662000802_0001/attempt_local662000802_0001_r_000000_0/output/map_31.out.merged of size 139586414
17/10/03 15:04:44 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local662000802_0001_m_000021_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/03 15:04:45 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local662000802_0001_m_000021_0
17/10/03 15:04:45 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 3, commitMemory -> 69793156, usedMemory ->104689838
17/10/03 15:04:45 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local662000802_0001_m_000020_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/03 15:04:45 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local662000802_0001_m_000020_0
17/10/03 15:04:45 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 4, commitMemory -> 104689838, usedMemory ->139586416
17/10/03 15:04:45 INFO reduce.MergeManagerImpl: Starting inMemoryMerger's merge since commitMemory=139586416 > mergeThreshold=123774960. Current usedMemory=139586416
17/10/03 15:04:45 INFO reduce.MergeThread: InMemoryMerger - Thread to merge in-memory shuffled map-outputs: Starting merge with 4 segments, while ignoring 0 segments
17/10/03 15:04:45 INFO reduce.MergeManagerImpl: Initiating in-memory merge with 4 segments...
17/10/03 15:04:45 INFO mapred.Merger: Merging 4 sorted segments
17/10/03 15:04:45 INFO mapred.Merger: Down to the last merge-pass, with 4 segments left of total size: 139586364 bytes
17/10/03 15:04:45 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local662000802_0001_m_000019_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/03 15:04:45 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local662000802_0001_m_000019_0
17/10/03 15:04:45 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 1, commitMemory -> 0, usedMemory ->174482994
17/10/03 15:04:45 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local662000802_0001_m_000007_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/03 15:04:45 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local662000802_0001_m_000007_0
17/10/03 15:04:45 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 2, commitMemory -> 34896578, usedMemory ->209379572
17/10/03 15:04:45 INFO reduce.LocalFetcher: fetcher#1 - MergeManager returned Status.WAIT ...
17/10/03 15:04:45 INFO mapreduce.Job:  map 100% reduce 23%
17/10/03 15:04:46 INFO reduce.MergeManagerImpl: attempt_local662000802_0001_r_000000_0 Merge of the 4 files in-memory complete. Local file is /tmp/hadoop-danielrozental/mapred/local/localRunner/danielrozental/jobcache/job_local662000802_0001/attempt_local662000802_0001_r_000000_0/output/map_22.out.merged of size 139586414
17/10/03 15:04:46 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local662000802_0001_m_000011_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/03 15:04:46 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local662000802_0001_m_000011_0
17/10/03 15:04:46 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 3, commitMemory -> 69793156, usedMemory ->104689838
17/10/03 15:04:46 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local662000802_0001_m_000025_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/03 15:04:46 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local662000802_0001_m_000025_0
17/10/03 15:04:46 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 4, commitMemory -> 104689838, usedMemory ->139586416
17/10/03 15:04:46 INFO reduce.MergeManagerImpl: Starting inMemoryMerger's merge since commitMemory=139586416 > mergeThreshold=123774960. Current usedMemory=139586416
17/10/03 15:04:46 INFO reduce.MergeThread: InMemoryMerger - Thread to merge in-memory shuffled map-outputs: Starting merge with 4 segments, while ignoring 0 segments
17/10/03 15:04:46 INFO reduce.MergeManagerImpl: Initiating in-memory merge with 4 segments...
17/10/03 15:04:46 INFO mapred.Merger: Merging 4 sorted segments
17/10/03 15:04:46 INFO mapred.Merger: Down to the last merge-pass, with 4 segments left of total size: 139586364 bytes
17/10/03 15:04:46 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local662000802_0001_m_000012_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/03 15:04:46 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local662000802_0001_m_000012_0
17/10/03 15:04:46 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 1, commitMemory -> 0, usedMemory ->174482994
17/10/03 15:04:46 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local662000802_0001_m_000024_0 decomp: 34896682 len: 34896686 to MEMORY
17/10/03 15:04:46 INFO reduce.InMemoryMapOutput: Read 34896682 bytes from map-output for attempt_local662000802_0001_m_000024_0
17/10/03 15:04:46 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896682, inMemoryMapOutputs.size() -> 2, commitMemory -> 34896578, usedMemory ->209379676
17/10/03 15:04:46 INFO reduce.LocalFetcher: fetcher#1 - MergeManager returned Status.WAIT ...
17/10/03 15:04:47 INFO reduce.MergeManagerImpl: attempt_local662000802_0001_r_000000_0 Merge of the 4 files in-memory complete. Local file is /tmp/hadoop-danielrozental/mapred/local/localRunner/danielrozental/jobcache/job_local662000802_0001/attempt_local662000802_0001_r_000000_0/output/map_19.out.merged of size 139586414
17/10/03 15:04:47 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local662000802_0001_m_000023_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/03 15:04:47 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local662000802_0001_m_000023_0
17/10/03 15:04:47 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 3, commitMemory -> 69793260, usedMemory ->104689838
17/10/03 15:04:47 INFO reduce.LocalFetcher: localfetcher#1 about to shuffle output of map attempt_local662000802_0001_m_000010_0 decomp: 34896578 len: 34896582 to MEMORY
17/10/03 15:04:47 INFO reduce.InMemoryMapOutput: Read 34896578 bytes from map-output for attempt_local662000802_0001_m_000010_0
17/10/03 15:04:47 INFO reduce.MergeManagerImpl: closeInMemoryFile -> map-output of size: 34896578, inMemoryMapOutputs.size() -> 4, commitMemory -> 104689838, usedMemory ->139586416
17/10/03 15:04:47 INFO reduce.MergeManagerImpl: Starting inMemoryMerger's merge since commitMemory=139586416 > mergeThreshold=123774960. Current usedMemory=139586416
17/10/03 15:04:47 INFO reduce.MergeThread: InMemoryMerger - Thread to merge in-memory shuffled map-outputs: Starting merge with 4 segments, while ignoring 0 segments
17/10/03 15:04:47 INFO reduce.EventFetcher: EventFetcher is interrupted.. Returning
17/10/03 15:04:47 INFO mapred.LocalJobRunner: 32 / 32 copied.
17/10/03 15:04:47 INFO reduce.MergeManagerImpl: Initiating in-memory merge with 4 segments...
17/10/03 15:04:47 INFO mapred.Merger: Merging 4 sorted segments
17/10/03 15:04:47 INFO mapred.Merger: Down to the last merge-pass, with 4 segments left of total size: 139586364 bytes
17/10/03 15:04:47 INFO mapred.LocalJobRunner: reduce > sort
17/10/03 15:04:48 INFO reduce.MergeManagerImpl: attempt_local662000802_0001_r_000000_0 Merge of the 4 files in-memory complete. Local file is /tmp/hadoop-danielrozental/mapred/local/localRunner/danielrozental/jobcache/job_local662000802_0001/attempt_local662000802_0001_r_000000_0/output/map_12.out.merged of size 139586414
17/10/03 15:04:48 INFO reduce.MergeManagerImpl: finalMerge called with 0 in-memory map-outputs and 8 on-disk map-outputs
17/10/03 15:04:48 INFO reduce.MergeManagerImpl: Merging 8 files, 1116691520 bytes from disk
17/10/03 15:04:48 INFO reduce.MergeManagerImpl: Merging 0 segments, 0 bytes from memory into reduce
17/10/03 15:04:48 INFO mapred.Merger: Merging 8 sorted segments
17/10/03 15:04:48 INFO mapred.Merger: Down to the last merge-pass, with 8 segments left of total size: 1116691384 bytes
17/10/03 15:04:48 INFO mapred.LocalJobRunner: reduce > sort
17/10/03 15:04:48 INFO Configuration.deprecation: mapred.skip.on is deprecated. Instead, use mapreduce.job.skiprecords
17/10/03 15:04:48 INFO mapreduce.Job:  map 100% reduce 33%
17/10/03 15:04:50 INFO mapred.LocalJobRunner: reduce > reduce
17/10/03 15:04:51 INFO mapreduce.Job:  map 100% reduce 71%
17/10/03 15:04:53 INFO mapred.LocalJobRunner: reduce > reduce
17/10/03 15:04:54 INFO mapreduce.Job:  map 100% reduce 78%
17/10/03 15:04:56 INFO mapred.LocalJobRunner: reduce > reduce
17/10/03 15:04:57 INFO mapreduce.Job:  map 100% reduce 85%
17/10/03 15:04:59 INFO mapred.LocalJobRunner: reduce > reduce
17/10/03 15:05:00 INFO mapreduce.Job:  map 100% reduce 91%
17/10/03 15:05:02 INFO mapred.LocalJobRunner: reduce > reduce
17/10/03 15:05:03 INFO mapreduce.Job:  map 100% reduce 98%
17/10/03 15:05:03 INFO mapred.Task: Task:attempt_local662000802_0001_r_000000_0 is done. And is in the process of committing
17/10/03 15:05:03 INFO mapred.LocalJobRunner: reduce > reduce
17/10/03 15:05:03 INFO mapred.Task: Task attempt_local662000802_0001_r_000000_0 is allowed to commit now
17/10/03 15:05:03 INFO output.FileOutputCommitter: Saved output of task 'attempt_local662000802_0001_r_000000_0' to hdfs://ip-172-31-1-236.us-east-2.compute.internal:8020/user/danielrozental/terasort/_temporary/0/task_local662000802_0001_r_000000
17/10/03 15:05:03 INFO mapred.LocalJobRunner: reduce > reduce
17/10/03 15:05:03 INFO mapred.Task: Task 'attempt_local662000802_0001_r_000000_0' done.
17/10/03 15:05:03 INFO mapred.LocalJobRunner: Finishing task: attempt_local662000802_0001_r_000000_0
17/10/03 15:05:03 INFO mapred.LocalJobRunner: reduce task executor complete.
17/10/03 15:05:04 INFO mapreduce.Job:  map 100% reduce 100%
17/10/03 15:05:04 INFO mapreduce.Job: Job job_local662000802_0001 completed successfully
17/10/03 15:05:04 INFO mapreduce.Job: Counters: 35
        File System Counters
                FILE: Number of bytes read=2244534646
                FILE: Number of bytes written=20678349880
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=19120481300
                HDFS: Number of bytes written=1073741800
                HDFS: Number of read operations=1948
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=68
        Map-Reduce Framework
                Map input records=10737418
                Map output records=10737418
                Map output bytes=1095216636
                Map output materialized bytes=1116691664
                Input split bytes=5120
                Combine input records=0
                Combine output records=0
                Reduce input groups=10737418
                Reduce shuffle bytes=1116691664
                Reduce input records=10737418
                Reduce output records=10737418
                Spilled Records=21474836
                Shuffled Maps =32
                Failed Shuffles=0
                Merged Map outputs=32
                GC time elapsed (ms)=2150
                Total committed heap usage (bytes)=8312586240
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
        File Input Format Counters
                Bytes Read=1073741800
        File Output Format Counters
                Bytes Written=1073741800
17/10/03 15:05:04 INFO terasort.TeraSort: done

real    1m0.190s
user    1m11.971s
sys     0m4.175s
```
