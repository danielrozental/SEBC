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

# 4. Seteos para que funcione distcp

Habilitamos dfs.client.use.datanode.hostname en la consola de wjguerrero

Modificamos el archivo de hosts desde donde ejecuto el comando

```
13.59.169.94 ip-172-31-6-242.us-east-2.compute.internal
13.58.229.204 ip-172-31-13-29.us-east-2.compute.internal
18.221.191.254 ip-172-31-5-64.us-east-2.compute.internal
18.220.117.96 ip-172-31-0-4.us-east-2.compute.internal
```

```
[hdfs@ip-172-31-11-253 centos]$ hadoop distcp hdfs://13.58.229.204:8020/user/hdf                                                                                    s/wjguerrero/teragen/part-m-00001 /user/hdfs/wjguerrero
17/10/03 14:23:50 INFO tools.DistCp: Input Options: DistCpOptions{atomicCommit=f                                                                                    alse, syncFolder=false, deleteMissing=false, ignoreFailures=false, overwrite=fal                                                                                    se, append=false, useDiff=false, useRdiff=false, fromSnapshot=null, toSnapshot=n                                                                                    ull, skipCRC=false, blocking=true, numListstatusThreads=0, maxMaps=20, mapBandwi                                                                                    dth=100, sslConfigurationFile='null', copyStrategy='uniformsize', preserveStatus                                                                                    =[], preserveRawXattrs=false, atomicWorkPath=null, logPath=null, sourceFileListi                                                                                    ng=null, sourcePaths=[hdfs://13.58.229.204:8020/user/hdfs/wjguerrero/teragen/par                                                                                    t-m-00001], targetPath=/user/hdfs/wjguerrero, targetPathExists=true, filtersFile                                                                                    ='null'}
17/10/03 14:23:50 INFO Configuration.deprecation: session.id is deprecated. Inst                                                                                    ead, use dfs.metrics.session-id
17/10/03 14:23:50 INFO jvm.JvmMetrics: Initializing JVM Metrics with processName                                                                                    =JobTracker, sessionId=
17/10/03 14:23:51 INFO tools.SimpleCopyListing: Paths (files+dirs) cnt = 1; dirC                                                                                    nt = 0
17/10/03 14:23:51 INFO tools.SimpleCopyListing: Build file listing completed.
17/10/03 14:23:51 INFO Configuration.deprecation: io.sort.mb is deprecated. Inst                                                                                    ead, use mapreduce.task.io.sort.mb
17/10/03 14:23:51 INFO Configuration.deprecation: io.sort.factor is deprecated.                                                                                     Instead, use mapreduce.task.io.sort.factor
17/10/03 14:23:51 INFO tools.DistCp: Number of paths in the copy list: 1
17/10/03 14:23:51 INFO tools.DistCp: Number of paths in the copy list: 1
17/10/03 14:23:51 INFO jvm.JvmMetrics: Cannot initialize JVM Metrics with proces                                                                                    sName=JobTracker, sessionId= - already initialized
17/10/03 14:23:51 INFO mapreduce.JobSubmitter: number of splits:1
17/10/03 14:23:51 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_lo                                                                                    cal1668468618_0001
17/10/03 14:23:51 INFO mapreduce.Job: The url to track the job: http://localhost                                                                                    :8080/
17/10/03 14:23:51 INFO tools.DistCp: DistCp job-id: job_local1668468618_0001
17/10/03 14:23:51 INFO mapreduce.Job: Running job: job_local1668468618_0001
17/10/03 14:23:51 INFO mapred.LocalJobRunner: OutputCommitter set in config null
17/10/03 14:23:51 INFO output.FileOutputCommitter: File Output Committer Algorit                                                                                    hm version is 1
17/10/03 14:23:51 INFO mapred.LocalJobRunner: OutputCommitter is org.apache.hado                                                                                    op.tools.mapred.CopyCommitter
17/10/03 14:23:51 INFO mapred.LocalJobRunner: Waiting for map tasks
17/10/03 14:23:51 INFO mapred.LocalJobRunner: Starting task: attempt_local166846                                                                                    8618_0001_m_000000_0
17/10/03 14:23:51 INFO output.FileOutputCommitter: File Output Committer Algorit                                                                                    hm version is 1
17/10/03 14:23:51 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/03 14:23:51 INFO mapred.MapTask: Processing split: file:/tmp/hadoop-hdfs/m                                                                                    apred/staging/hdfs584526043/.staging/_distcp170703173/fileList.seq:0+247
17/10/03 14:23:51 INFO output.FileOutputCommitter: File Output Committer Algorit                                                                                    hm version is 1
17/10/03 14:23:51 INFO mapred.CopyMapper: Copying hdfs://13.58.229.204:8020/user                                                                                    /hdfs/wjguerrero/teragen/part-m-00001 to hdfs://ip-172-31-1-236.us-east-2.comput                                                                                    e.internal:8020/user/hdfs/wjguerrero/part-m-00001
17/10/03 14:23:51 INFO mapred.RetriableFileCopyCommand: Creating temp file: hdfs                                                                                    ://ip-172-31-1-236.us-east-2.compute.internal:8020/user/hdfs/wjguerrero/.distcp.                                                                                    tmp.attempt_local1668468618_0001_m_000000_0
17/10/03 14:23:52 INFO mapreduce.Job: Job job_local1668468618_0001 running in ub                                                                                    er mode : false
17/10/03 14:23:52 INFO mapreduce.Job:  map 0% reduce 0%
17/10/03 14:23:55 INFO mapred.LocalJobRunner:
17/10/03 14:23:55 INFO mapred.Task: Task:attempt_local1668468618_0001_m_000000_0                                                                                     is done. And is in the process of committing
17/10/03 14:23:55 INFO mapred.LocalJobRunner:
17/10/03 14:23:55 INFO mapred.Task: Task attempt_local1668468618_0001_m_000000_0                                                                                     is allowed to commit now
17/10/03 14:23:55 INFO output.FileOutputCommitter: Saved output of task 'attempt                                                                                    _local1668468618_0001_m_000000_0' to file:/tmp/hadoop-hdfs/mapred/staging/hdfs58                                                                                    4526043/.staging/_distcp170703173/_logs/_temporary/0/task_local1668468618_0001_m                                                                                    _000000
17/10/03 14:23:55 INFO mapred.LocalJobRunner: 100.0% Copying hdfs://13.58.229.20                                                                                    4:8020/user/hdfs/wjguerrero/teragen/part-m-00001 to hdfs://ip-172-31-1-236.us-ea                                                                                    st-2.compute.internal:8020/user/hdfs/wjguerrero/part-m-00001 [250.0M/250.0M]
17/10/03 14:23:55 INFO mapred.Task: Task 'attempt_local1668468618_0001_m_000000_                                                                                    0' done.
17/10/03 14:23:55 INFO mapred.LocalJobRunner: Finishing task: attempt_local16684                                                                                    68618_0001_m_000000_0
17/10/03 14:23:55 INFO mapred.LocalJobRunner: map task executor complete.
17/10/03 14:23:55 INFO mapred.CopyCommitter: Cleaning up temporary work folder:                                                                                     file:/tmp/hadoop-hdfs/mapred/staging/hdfs584526043/.staging/_distcp170703173
17/10/03 14:23:55 INFO mapreduce.Job:  map 100% reduce 0%
17/10/03 14:23:55 INFO mapreduce.Job: Job job_local1668468618_0001 completed suc                                                                                    cessfully
17/10/03 14:23:55 INFO mapreduce.Job: Counters: 23
        File System Counters
                FILE: Number of bytes read=1957641
                FILE: Number of bytes written=2267051
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=262144000
                HDFS: Number of bytes written=262144000
                HDFS: Number of read operations=20
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=2
        Map-Reduce Framework
                Map input records=1
                Map output records=0
                Input split bytes=154
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=36
                Total committed heap usage (bytes)=257425408
        File Input Format Counters
                Bytes Read=279
        File Output Format Counters
                Bytes Written=8
        org.apache.hadoop.tools.mapred.CopyMapper$Counter
                BYTESCOPIED=262144000
                BYTESEXPECTED=262144000
                COPY=1
```

```
[hdfs@ip-172-31-11-253 centos]$ hdfs dfs -ls /user/hdfs/wjguerrero
Found 5 items
-rw-r--r--   3 hdfs supergroup          0 2017-10-03 14:12 /user/hdfs/wjguerrero/.distcp.tmp.attempt_local1445819241_0001_m_000000_0
-rw-r--r--   3 hdfs supergroup          0 2017-10-03 14:02 /user/hdfs/wjguerrero/.distcp.tmp.attempt_local1808963728_0001_m_000000_0
-rw-r--r--   3 hdfs supergroup          0 2017-10-03 14:19 /user/hdfs/wjguerrero/.distcp.tmp.attempt_local2145125088_0001_m_000000_0
-rw-r--r--   3 hdfs supergroup          0 2017-10-03 14:17 /user/hdfs/wjguerrero/.distcp.tmp.attempt_local521761410_0001_m_000000_0
-rw-r--r--   3 hdfs supergroup  262144000 2017-10-03 14:23 /user/hdfs/wjguerrero/part-m-00001
```