# 1. Creo los directorios

[hdfs@ip-172-31-11-253 centos]$ sudo su hdfs
[hdfs@ip-172-31-11-253 centos]$ hdfs dfs -mkdir -p /user/hdfs
[hdfs@ip-172-31-11-253 centos]$ hdfs dfs -mkdir /user/hdfs/danielrozental
[hdfs@ip-172-31-11-253 centos]$ hdfs dfs -mkdir /user/hdfs/wjguerrero
[hdfs@ip-172-31-11-253 centos]$ hdfs dfs -ls
Found 2 items
drwxr-xr-x   - hdfs supergroup          0 2017-10-03 13:23 danielrozental
drwxr-xr-x   - hdfs supergroup          0 2017-10-03 13:23 wjguerrero

# 2. Ejecuto teragen

```
[hdfs@ip-172-31-11-253 jars]$ hadoop jar /disco1/cloudera/parcels/CDH/jars/hadoop-examples.jar teragen 5242880 /user/hdfs/danielrozental/teragen
17/10/03 13:40:27 INFO Configuration.deprecation: session.id is deprecated. Instead, use dfs.metrics.session-id
17/10/03 13:40:27 INFO jvm.JvmMetrics: Initializing JVM Metrics with processName=JobTracker, sessionId=
17/10/03 13:40:27 INFO terasort.TeraSort: Generating 5242880 using 1
17/10/03 13:40:27 INFO mapreduce.JobSubmitter: number of splits:1
17/10/03 13:40:27 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_local1190829612_0001
17/10/03 13:40:27 INFO mapreduce.Job: The url to track the job: http://localhost:8080/
17/10/03 13:40:27 INFO mapreduce.Job: Running job: job_local1190829612_0001
17/10/03 13:40:27 INFO mapred.LocalJobRunner: OutputCommitter set in config null
17/10/03 13:40:27 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/03 13:40:27 INFO mapred.LocalJobRunner: OutputCommitter is org.apache.hadoop.mapreduce.lib.output.FileOutputCommitter
17/10/03 13:40:27 INFO mapred.LocalJobRunner: Waiting for map tasks
17/10/03 13:40:27 INFO mapred.LocalJobRunner: Starting task: attempt_local1190829612_0001_m_000000_0
17/10/03 13:40:27 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/03 13:40:27 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/03 13:40:27 INFO mapred.MapTask: Processing split: org.apache.hadoop.examples.terasort.TeraGen$RangeInputFormat$RangeInputSplit@5c3e95fd
17/10/03 13:40:28 INFO mapreduce.Job: Job job_local1190829612_0001 running in uber mode : false
17/10/03 13:40:28 INFO mapreduce.Job:  map 0% reduce 0%
17/10/03 13:40:32 INFO mapred.LocalJobRunner:
17/10/03 13:40:32 INFO mapred.Task: Task:attempt_local1190829612_0001_m_000000_0 is done. And is in the process of committing
17/10/03 13:40:32 INFO mapred.LocalJobRunner:
17/10/03 13:40:32 INFO mapred.Task: Task attempt_local1190829612_0001_m_000000_0 is allowed to commit now
17/10/03 13:40:32 INFO output.FileOutputCommitter: Saved output of task 'attempt_local1190829612_0001_m_000000_0' to hdfs://ip-172-31-1-236.us-east-2.compute.internal:8020/user/hdfs/danielrozental/teragen/_temporary/0/task_local1190829612_0001_m_000000
17/10/03 13:40:32 INFO mapred.LocalJobRunner: map
17/10/03 13:40:32 INFO mapred.Task: Task 'attempt_local1190829612_0001_m_000000_0' done.
17/10/03 13:40:32 INFO mapred.LocalJobRunner: Finishing task: attempt_local1190829612_0001_m_000000_0
17/10/03 13:40:32 INFO mapred.LocalJobRunner: map task executor complete.
17/10/03 13:40:33 INFO mapreduce.Job:  map 100% reduce 0%
17/10/03 13:40:33 INFO mapreduce.Job: Job job_local1190829612_0001 completed successfully
17/10/03 13:40:33 INFO mapreduce.Job: Counters: 21
        File System Counters
                FILE: Number of bytes read=276332
                FILE: Number of bytes written=565456
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=0
                HDFS: Number of bytes written=524288000
                HDFS: Number of read operations=4
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=3
        Map-Reduce Framework
                Map input records=5242880
                Map output records=5242880
                Input split bytes=82
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=69
                Total committed heap usage (bytes)=223346688
        org.apache.hadoop.examples.terasort.TeraGen$Counters
                CHECKSUM=11257830824958050
        File Input Format Counters
                Bytes Read=0
        File Output Format Counters
                Bytes Written=524288000
```

# 3. Verifico archivo generado

```				
[hdfs@ip-172-31-11-253 jars]$ hdfs dfs -ls danielrozental/teragen
Found 2 items
-rw-r--r--   3 hdfs supergroup          0 2017-10-03 13:40 danielrozental/teragen/_SUCCESS
-rw-r--r--   3 hdfs supergroup  524288000 2017-10-03 13:40 danielrozental/teragen/part-m-00000
```
