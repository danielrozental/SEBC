```
time hadoop jar /disco1/cloudera/parcels/CDH/jars/hadoop-examples.jar terasort /user/saturn/tgen2 /user/saturn/tsort

time hadoop jar /disco1/cloudera/parcels/CDH/jars/hadoop-examples.jar terasort -Dmapreduce.reduce.shuffle.input.buffer.percent=0.25  /user/saturn/tgen2 /user/saturn/tsort

[saturn@ip-172-31-35-215 yarn]$ time hadoop jar /disco1/cloudera/parcels/CDH/jars/hadoop-examples.jar terasort /user/saturn/tgen2 /user/saturn/tsort
17/10/06 15:42:22 INFO terasort.TeraSort: starting
17/10/06 15:42:23 INFO hdfs.DFSClient: Created token for saturn: HDFS_DELEGATION_TOKEN owner=saturn@DANIELROZENTAL.HQ, renewer=yarn, realUser=, issueDate=1507304543891, maxDate=1507909343891, sequenceNumber=3, masterKeyId=2 on 172.31.33.183:8020
17/10/06 15:42:23 INFO security.TokenCache: Got dt for hdfs://ip-172-31-33-183.us-east-2.compute.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.33.183:8020, Ident: (token for saturn: HDFS_DELEGATION_TOKEN owner=saturn@DANIELROZENTAL.HQ, renewer=yarn, realUser=, issueDate=1507304543891, maxDate=1507909343891, sequenceNumber=3, masterKeyId=2)
17/10/06 15:42:24 INFO input.FileInputFormat: Total input paths to process : 12
Spent 305ms computing base-splits.
Spent 3ms computing TeraScheduler splits.
Computing input splits took 309ms
Sampling 10 splits of 204
Making 12 from 100000 sampled records
Computing parititions took 535ms
Spent 845ms computing partitions.
17/10/06 15:42:24 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-35-215.us-east-2.compute.internal/172.31.35.215:8032
17/10/06 15:42:24 INFO mapreduce.JobSubmitter: number of splits:204
17/10/06 15:42:25 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1507303969493_0003
17/10/06 15:42:25 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.33.183:8020, Ident: (token for saturn: HDFS_DELEGATION_TOKEN owner=saturn@DANIELROZENTAL.HQ, renewer=yarn, realUser=, issueDate=1507304543891, maxDate=1507909343891, sequenceNumber=3, masterKeyId=2)
17/10/06 15:42:25 INFO impl.YarnClientImpl: Submitted application application_1507303969493_0003
17/10/06 15:42:25 INFO mapreduce.Job: The url to track the job: http://ip-172-31-35-215.us-east-2.compute.internal:8088/proxy/application_1507303969493_0003/
17/10/06 15:42:25 INFO mapreduce.Job: Running job: job_1507303969493_0003
17/10/06 15:42:31 INFO mapreduce.Job: Job job_1507303969493_0003 running in uber mode : false
17/10/06 15:42:31 INFO mapreduce.Job:  map 0% reduce 0%
17/10/06 15:42:47 INFO mapreduce.Job:  map 5% reduce 0%
17/10/06 15:42:48 INFO mapreduce.Job:  map 7% reduce 0%
17/10/06 15:42:49 INFO mapreduce.Job:  map 11% reduce 0%
17/10/06 15:43:03 INFO mapreduce.Job:  map 15% reduce 0%
17/10/06 15:43:04 INFO mapreduce.Job:  map 18% reduce 0%
17/10/06 15:43:06 INFO mapreduce.Job:  map 21% reduce 0%
17/10/06 15:43:07 INFO mapreduce.Job:  map 22% reduce 0%
17/10/06 15:43:17 INFO mapreduce.Job:  map 25% reduce 0%
17/10/06 15:43:18 INFO mapreduce.Job:  map 26% reduce 0%
17/10/06 15:43:19 INFO mapreduce.Job:  map 28% reduce 0%
17/10/06 15:43:22 INFO mapreduce.Job:  map 32% reduce 0%
17/10/06 15:43:31 INFO mapreduce.Job:  map 33% reduce 0%
17/10/06 15:43:32 INFO mapreduce.Job:  map 36% reduce 0%
17/10/06 15:43:33 INFO mapreduce.Job:  map 38% reduce 0%
17/10/06 15:43:34 INFO mapreduce.Job:  map 39% reduce 0%
17/10/06 15:43:38 INFO mapreduce.Job:  map 43% reduce 0%
17/10/06 15:43:45 INFO mapreduce.Job:  map 44% reduce 0%
17/10/06 15:43:46 INFO mapreduce.Job:  map 47% reduce 0%
17/10/06 15:43:48 INFO mapreduce.Job:  map 50% reduce 0%
17/10/06 15:43:54 INFO mapreduce.Job:  map 54% reduce 0%
17/10/06 15:44:00 INFO mapreduce.Job:  map 57% reduce 0%
17/10/06 15:44:03 INFO mapreduce.Job:  map 60% reduce 0%
17/10/06 15:44:04 INFO mapreduce.Job:  map 61% reduce 0%
17/10/06 15:44:11 INFO mapreduce.Job:  map 65% reduce 0%
17/10/06 15:44:15 INFO mapreduce.Job:  map 68% reduce 0%
17/10/06 15:44:16 INFO mapreduce.Job:  map 69% reduce 0%
17/10/06 15:44:17 INFO mapreduce.Job:  map 72% reduce 0%
17/10/06 15:44:26 INFO mapreduce.Job:  map 73% reduce 0%
17/10/06 15:44:27 INFO mapreduce.Job:  map 75% reduce 0%
17/10/06 15:44:29 INFO mapreduce.Job:  map 79% reduce 0%
17/10/06 15:44:31 INFO mapreduce.Job:  map 82% reduce 0%
17/10/06 15:44:42 INFO mapreduce.Job:  map 86% reduce 0%
17/10/06 15:44:43 INFO mapreduce.Job:  map 90% reduce 0%
17/10/06 15:44:44 INFO mapreduce.Job:  map 91% reduce 0%
17/10/06 15:44:45 INFO mapreduce.Job:  map 93% reduce 0%
17/10/06 15:44:54 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_r_000006_0, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#9
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1912)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:391)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:306)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 15:44:54 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_r_000009_0, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#1
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1912)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:391)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:306)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 15:44:54 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_r_000010_0, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#6
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1912)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:391)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:306)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 15:44:54 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000010_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000008_0 from host ip-172-31-35-215.us-east-2.compute.internal
17/10/06 15:44:54 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000017_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000008_0 from host ip-172-31-35-215.us-east-2.compute.internal
17/10/06 15:44:54 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_r_000008_0, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#9
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1912)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:391)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:306)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 15:44:55 INFO mapreduce.Job:  map 92% reduce 0%
17/10/06 15:44:55 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000021_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000005_0 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:44:55 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000009_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000005_0 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:44:55 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000018_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000005_0 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:44:55 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000004_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000005_0 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:44:55 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000005_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000005_0 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:44:55 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000048_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000001_0 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:44:55 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000049_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000001_0 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:44:55 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000035_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000001_0 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:44:56 INFO mapreduce.Job:  map 75% reduce 0%
17/10/06 15:44:56 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000050_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000001_0 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:44:56 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000034_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000001_0 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:44:56 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000051_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000001_0 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:44:56 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000045_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000001_0 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:44:56 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000033_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000001_0 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:44:56 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000027_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000001_0 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:44:56 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000046_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000001_0 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:44:56 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000032_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000001_0 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:44:56 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000026_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000001_0 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:44:56 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000031_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000001_0 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:44:57 INFO mapreduce.Job:  map 71% reduce 0%
17/10/06 15:44:57 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_r_000005_0, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#2
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1912)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:391)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:306)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 15:44:57 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000013_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000007_0 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:44:57 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000000_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000007_0 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:44:57 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000001_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000007_0 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:44:57 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000008_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000007_0 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:44:57 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000007_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000007_0 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:44:57 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000019_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000007_0 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:44:57 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000044_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000007_0 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:44:57 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_r_000007_0, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#9
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1912)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:391)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:306)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 15:44:57 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000043_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000002_0 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:44:58 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000037_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000002_0 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:44:58 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000036_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000002_0 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:44:58 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000006_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000002_0 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:44:58 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000042_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000002_0 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:44:58 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000014_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000002_0 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:44:58 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000041_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000002_0 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:44:58 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000040_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000002_0 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:44:58 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000039_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000002_0 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:44:58 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000065_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000002_0 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:44:58 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000038_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000002_0 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:44:59 INFO mapreduce.Job:  map 75% reduce 0%
17/10/06 15:44:59 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000071_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000002_0 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:44:59 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_r_000001_0, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#8
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1912)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:391)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:306)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 15:44:59 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_r_000002_0, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#3
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1912)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:391)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:306)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 15:44:59 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_r_000003_0, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#10
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1912)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:391)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:306)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 15:44:59 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_r_000004_0, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#10
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1912)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:391)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:306)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 15:44:59 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000016_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000000_0 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:44:59 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000020_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000000_0 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:44:59 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000012_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000000_0 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:44:59 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000015_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000000_0 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:44:59 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000003_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000000_0 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:00 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000011_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000000_0 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:00 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000002_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000000_0 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:00 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000061_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000000_0 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:00 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000064_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000000_0 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:00 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000058_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000000_0 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:00 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_r_000000_0, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#9
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1912)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:391)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:306)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 15:45:05 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000072_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000008_1 from host ip-172-31-35-215.us-east-2.compute.internal
17/10/06 15:45:05 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000067_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000008_1 from host ip-172-31-35-215.us-east-2.compute.internal
17/10/06 15:45:05 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000022_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000008_1 from host ip-172-31-35-215.us-east-2.compute.internal
17/10/06 15:45:05 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_r_000008_1, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#2
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1912)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:391)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:306)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 15:45:06 INFO mapreduce.Job:  map 73% reduce 0%
17/10/06 15:45:08 INFO mapreduce.Job:  map 75% reduce 0%
17/10/06 15:45:08 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000023_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:08 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000030_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:08 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000024_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:08 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000028_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:08 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000025_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:08 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000029_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:08 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000115_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:09 INFO mapreduce.Job:  map 56% reduce 0%
17/10/06 15:45:09 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000091_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:09 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000089_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:09 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000116_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:09 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000110_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:09 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000069_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:09 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000090_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:09 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000068_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:09 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000070_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:09 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000111_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:09 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000094_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:10 INFO mapreduce.Job:  map 53% reduce 0%
17/10/06 15:45:10 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000112_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:10 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000088_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:10 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000113_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:10 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000092_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:10 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000066_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:10 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000093_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:10 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000114_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:10 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000084_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:10 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000102_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:10 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000109_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:11 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000060_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:11 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000085_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:11 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000062_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:11 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000083_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:11 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000103_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:11 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000106_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:11 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000087_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:11 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000082_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:11 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000081_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:11 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000063_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:12 INFO mapreduce.Job:  map 56% reduce 0%
17/10/06 15:45:12 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000105_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:12 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000059_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:12 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000080_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:12 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000086_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:12 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_r_000010_1, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#10
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1912)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:391)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:306)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 15:45:12 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000054_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000009_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:12 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000047_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000009_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:12 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000055_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000009_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:12 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000057_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000009_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:12 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000052_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000009_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:13 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000053_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000009_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:45:13 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_r_000009_1, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#10
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1912)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:391)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:306)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 15:45:14 INFO mapreduce.Job:  map 59% reduce 0%
17/10/06 15:45:21 INFO mapreduce.Job:  map 62% reduce 0%
17/10/06 15:45:22 INFO mapreduce.Job:  map 63% reduce 0%
17/10/06 15:45:26 INFO mapreduce.Job:  map 64% reduce 0%
17/10/06 15:45:27 INFO mapreduce.Job:  map 66% reduce 0%
17/10/06 15:45:28 INFO mapreduce.Job:  map 67% reduce 0%
17/10/06 15:45:29 INFO mapreduce.Job:  map 70% reduce 0%
17/10/06 15:45:35 INFO mapreduce.Job:  map 74% reduce 0%
17/10/06 15:45:43 INFO mapreduce.Job:  map 77% reduce 0%
17/10/06 15:45:44 INFO mapreduce.Job:  map 79% reduce 0%
17/10/06 15:45:45 INFO mapreduce.Job:  map 80% reduce 0%
17/10/06 15:45:49 INFO mapreduce.Job:  map 81% reduce 0%
17/10/06 15:45:50 INFO mapreduce.Job:  map 84% reduce 0%
17/10/06 15:45:58 INFO mapreduce.Job:  map 88% reduce 0%
17/10/06 15:45:59 INFO mapreduce.Job:  map 91% reduce 0%
17/10/06 15:46:04 INFO mapreduce.Job:  map 93% reduce 0%
17/10/06 15:46:05 INFO mapreduce.Job:  map 95% reduce 0%
17/10/06 15:46:10 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000132_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000004_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:46:10 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000134_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000004_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:46:10 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000108_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000004_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:46:10 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000104_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000004_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:46:10 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000107_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000004_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:46:10 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_r_000004_1, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#1
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1912)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:391)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:306)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 15:46:11 INFO mapreduce.Job:  map 93% reduce 0%
17/10/06 15:46:11 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_r_000003_1, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#1
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1912)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:391)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:306)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 15:46:11 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_r_000000_1, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#1
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1912)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:391)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:306)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 15:46:11 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_r_000006_1, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#8
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1912)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:391)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:306)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 15:46:12 INFO mapreduce.Job:  map 96% reduce 0%
17/10/06 15:46:14 INFO mapreduce.Job:  map 98% reduce 0%
17/10/06 15:46:15 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_r_000009_2, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#10
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1912)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:391)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:306)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 15:46:15 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000138_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_2 from host ip-172-31-35-215.us-east-2.compute.internal
17/10/06 15:46:15 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000056_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_2 from host ip-172-31-35-215.us-east-2.compute.internal
17/10/06 15:46:15 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000130_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_2 from host ip-172-31-35-215.us-east-2.compute.internal
17/10/06 15:46:15 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000126_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_2 from host ip-172-31-35-215.us-east-2.compute.internal
17/10/06 15:46:15 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000129_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_2 from host ip-172-31-35-215.us-east-2.compute.internal
17/10/06 15:46:15 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000131_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_2 from host ip-172-31-35-215.us-east-2.compute.internal
17/10/06 15:46:15 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000125_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_2 from host ip-172-31-35-215.us-east-2.compute.internal
17/10/06 15:46:15 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000128_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_2 from host ip-172-31-35-215.us-east-2.compute.internal
17/10/06 15:46:15 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000127_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_2 from host ip-172-31-35-215.us-east-2.compute.internal
17/10/06 15:46:16 INFO mapreduce.Job:  map 81% reduce 0%
17/10/06 15:46:16 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000124_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_2 from host ip-172-31-35-215.us-east-2.compute.internal
17/10/06 15:46:16 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000075_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000008_2 from host ip-172-31-35-215.us-east-2.compute.internal
17/10/06 15:46:16 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000078_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000008_2 from host ip-172-31-35-215.us-east-2.compute.internal
17/10/06 15:46:16 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000077_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000008_2 from host ip-172-31-35-215.us-east-2.compute.internal
17/10/06 15:46:16 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000074_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000008_2 from host ip-172-31-35-215.us-east-2.compute.internal
17/10/06 15:46:16 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000079_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000008_2 from host ip-172-31-35-215.us-east-2.compute.internal
17/10/06 15:46:16 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_r_000010_2, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#9
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1912)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:391)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:306)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 15:46:16 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_r_000008_2, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#9
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1912)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:391)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:306)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 15:46:16 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000159_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000007_1 from host ip-172-31-35-215.us-east-2.compute.internal
17/10/06 15:46:16 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000133_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000007_1 from host ip-172-31-35-215.us-east-2.compute.internal
17/10/06 15:46:17 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000135_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000007_1 from host ip-172-31-35-215.us-east-2.compute.internal
17/10/06 15:46:17 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000136_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000007_1 from host ip-172-31-35-215.us-east-2.compute.internal
17/10/06 15:46:17 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000137_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000007_1 from host ip-172-31-35-215.us-east-2.compute.internal
17/10/06 15:46:17 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000076_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000007_1 from host ip-172-31-35-215.us-east-2.compute.internal
17/10/06 15:46:17 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_r_000007_1, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#1
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1912)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:391)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:306)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 15:46:17 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000150_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000002_1 from host ip-172-31-35-215.us-east-2.compute.internal
17/10/06 15:46:17 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000146_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000002_1 from host ip-172-31-35-215.us-east-2.compute.internal
17/10/06 15:46:17 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000174_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000002_1 from host ip-172-31-35-215.us-east-2.compute.internal
17/10/06 15:46:17 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000152_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000002_1 from host ip-172-31-35-215.us-east-2.compute.internal
17/10/06 15:46:17 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000151_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000002_1 from host ip-172-31-35-215.us-east-2.compute.internal
17/10/06 15:46:18 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000147_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000002_1 from host ip-172-31-35-215.us-east-2.compute.internal
17/10/06 15:46:18 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000153_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000002_1 from host ip-172-31-35-215.us-east-2.compute.internal
17/10/06 15:46:18 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000149_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000002_1 from host ip-172-31-35-215.us-east-2.compute.internal
17/10/06 15:46:18 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000148_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000002_1 from host ip-172-31-35-215.us-east-2.compute.internal
17/10/06 15:46:18 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000073_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000002_1 from host ip-172-31-35-215.us-east-2.compute.internal
17/10/06 15:46:18 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_r_000002_1, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#8
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1912)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:391)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:306)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 15:46:18 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000172_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000001_1 from host ip-172-31-35-215.us-east-2.compute.internal
17/10/06 15:46:18 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000170_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000001_1 from host ip-172-31-35-215.us-east-2.compute.internal
17/10/06 15:46:18 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000175_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000001_1 from host ip-172-31-35-215.us-east-2.compute.internal
17/10/06 15:46:18 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_r_000001_1, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#10
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1912)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:391)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:306)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 15:46:19 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_r_000011_0, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#10
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1912)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:391)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:306)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 15:46:21 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000157_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000004_2 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:46:21 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000156_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000004_2 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:46:21 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000179_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000004_2 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:46:21 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000180_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000004_2 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:46:21 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000181_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000004_2 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:46:21 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000158_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000004_2 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:46:21 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000154_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000004_2 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:46:21 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000160_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000004_2 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:46:21 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000155_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000004_2 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:46:21 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000096_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000004_2 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:46:22 INFO mapreduce.Job:  map 62% reduce 0%
17/10/06 15:46:22 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000095_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000004_2 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:46:22 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000098_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000004_2 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:46:22 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000097_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000004_2 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:46:22 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000099_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000004_2 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:46:22 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000101_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000004_2 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:46:22 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000100_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000004_2 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:46:22 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_r_000004_2, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#8
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1912)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:391)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:306)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 15:46:22 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000171_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000005_1 from host ip-172-31-35-215.us-east-2.compute.internal
17/10/06 15:46:22 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000169_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000006_2 from host ip-172-31-35-178.us-east-2.compute.internal
17/10/06 15:46:22 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000173_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000006_2 from host ip-172-31-35-178.us-east-2.compute.internal
17/10/06 15:46:23 INFO mapreduce.Job:  map 61% reduce 0%
17/10/06 15:46:23 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000168_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000006_2 from host ip-172-31-35-178.us-east-2.compute.internal
17/10/06 15:46:23 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000182_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000006_2 from host ip-172-31-35-178.us-east-2.compute.internal
17/10/06 15:46:23 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000176_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000006_2 from host ip-172-31-35-178.us-east-2.compute.internal
17/10/06 15:46:23 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000177_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000006_2 from host ip-172-31-35-178.us-east-2.compute.internal
17/10/06 15:46:23 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000178_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000006_2 from host ip-172-31-35-178.us-east-2.compute.internal
17/10/06 15:46:23 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000145_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000006_2 from host ip-172-31-35-178.us-east-2.compute.internal
17/10/06 15:46:23 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000143_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000006_2 from host ip-172-31-35-178.us-east-2.compute.internal
17/10/06 15:46:23 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000117_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000006_2 from host ip-172-31-35-178.us-east-2.compute.internal
17/10/06 15:46:23 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000144_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000006_2 from host ip-172-31-35-178.us-east-2.compute.internal
17/10/06 15:46:23 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000118_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000006_2 from host ip-172-31-35-178.us-east-2.compute.internal
17/10/06 15:46:24 INFO mapreduce.Job:  map 62% reduce 0%
17/10/06 15:46:24 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000123_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000006_2 from host ip-172-31-35-178.us-east-2.compute.internal
17/10/06 15:46:24 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000140_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000006_2 from host ip-172-31-35-178.us-east-2.compute.internal
17/10/06 15:46:24 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000122_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000006_2 from host ip-172-31-35-178.us-east-2.compute.internal
17/10/06 15:46:24 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000119_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000006_2 from host ip-172-31-35-178.us-east-2.compute.internal
17/10/06 15:46:24 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000121_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000006_2 from host ip-172-31-35-178.us-east-2.compute.internal
17/10/06 15:46:24 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000120_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000006_2 from host ip-172-31-35-178.us-east-2.compute.internal
17/10/06 15:46:24 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_r_000006_2, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#9
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1912)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:391)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:306)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 15:46:24 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000192_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000000_2 from host ip-172-31-35-178.us-east-2.compute.internal
17/10/06 15:46:24 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000193_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000000_2 from host ip-172-31-35-178.us-east-2.compute.internal
17/10/06 15:46:24 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000139_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000000_2 from host ip-172-31-35-178.us-east-2.compute.internal
17/10/06 15:46:26 INFO mapreduce.Job:  map 64% reduce 0%
17/10/06 15:46:26 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000141_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000000_2 from host ip-172-31-35-178.us-east-2.compute.internal
17/10/06 15:46:26 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_r_000000_2, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#2
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1912)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:391)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:306)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 15:46:26 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000142_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000003_2 from host ip-172-31-35-178.us-east-2.compute.internal
17/10/06 15:46:26 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_r_000003_2, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#1
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1912)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:391)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:306)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 15:46:29 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_r_000005_1, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#9
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1912)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:391)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:306)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 15:46:30 INFO mapreduce.Job:  map 66% reduce 0%
17/10/06 15:46:31 INFO mapreduce.Job:  map 67% reduce 0%
17/10/06 15:46:33 INFO mapreduce.Job:  map 68% reduce 0%
17/10/06 15:46:34 INFO mapreduce.Job:  map 70% reduce 0%
17/10/06 15:46:38 INFO mapreduce.Job:  map 73% reduce 0%
17/10/06 15:46:39 INFO mapreduce.Job:  map 74% reduce 0%
17/10/06 15:46:45 INFO mapreduce.Job:  map 77% reduce 0%
17/10/06 15:46:46 INFO mapreduce.Job:  map 78% reduce 0%
17/10/06 15:46:49 INFO mapreduce.Job:  map 79% reduce 0%
17/10/06 15:46:50 INFO mapreduce.Job:  map 80% reduce 0%
17/10/06 15:46:53 INFO mapreduce.Job:  map 83% reduce 0%
17/10/06 15:46:54 INFO mapreduce.Job:  map 84% reduce 0%
17/10/06 15:46:55 INFO mapreduce.Job:  map 85% reduce 0%
17/10/06 15:46:59 INFO mapreduce.Job:  map 88% reduce 0%
17/10/06 15:47:00 INFO mapreduce.Job:  map 89% reduce 0%
17/10/06 15:47:05 INFO mapreduce.Job:  map 91% reduce 0%
17/10/06 15:47:06 INFO mapreduce.Job:  map 92% reduce 0%
17/10/06 15:47:07 INFO mapreduce.Job:  map 94% reduce 0%
17/10/06 15:47:10 INFO mapreduce.Job:  map 95% reduce 0%
17/10/06 15:47:11 INFO mapreduce.Job:  map 96% reduce 0%
17/10/06 15:47:12 INFO mapreduce.Job:  map 97% reduce 0%
17/10/06 15:47:13 INFO mapreduce.Job:  map 100% reduce 0%
17/10/06 15:47:16 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000203_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000007_2 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:47:16 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000191_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000007_2 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:47:16 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000201_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000007_2 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:47:16 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000017_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000007_2 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:47:16 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000202_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000007_2 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:47:16 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000190_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000007_2 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:47:16 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_r_000007_2, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#1
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1912)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:391)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:306)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 15:47:16 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000021_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000001_2 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:47:16 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000010_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000001_2 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:47:16 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000048_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000001_2 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:47:17 INFO mapreduce.Job:  map 100% reduce 100%
17/10/06 15:47:17 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000051_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000001_2 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:47:17 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000009_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000001_2 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:47:17 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000004_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000001_2 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:47:17 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000018_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000001_2 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:47:17 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000167_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000001_2 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:47:17 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_r_000001_2, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#2
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1912)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:391)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:306)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 15:47:17 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000043_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000011_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:47:17 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000037_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000011_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:47:17 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000036_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000011_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:47:17 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000008_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000011_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:47:18 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000007_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000011_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:47:18 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000044_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000011_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:47:18 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000005_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000011_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:47:18 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000019_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000011_1 from host ip-172-31-33-183.us-east-2.compute.internal
17/10/06 15:47:18 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_r_000011_1, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#9
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1912)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:391)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:306)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 15:47:18 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_r_000002_2, Status : FAILED
Error: org.apache.hadoop.mapreduce.task.reduce.Shuffle$ShuffleError: error in shuffle in fetcher#9
        at org.apache.hadoop.mapreduce.task.reduce.Shuffle.run(Shuffle.java:134)
        at org.apache.hadoop.mapred.ReduceTask.run(ReduceTask.java:376)
        at org.apache.hadoop.mapred.YarnChild$2.run(YarnChild.java:164)
        at java.security.AccessController.doPrivileged(Native Method)
        at javax.security.auth.Subject.doAs(Subject.java:415)
        at org.apache.hadoop.security.UserGroupInformation.doAs(UserGroupInformation.java:1912)
        at org.apache.hadoop.mapred.YarnChild.main(YarnChild.java:158)
Caused by: java.io.IOException: Exceeded MAX_FAILED_UNIQUE_FETCHES; bailing-out.
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.checkReducerHealth(ShuffleSchedulerImpl.java:391)
        at org.apache.hadoop.mapreduce.task.reduce.ShuffleSchedulerImpl.copyFailed(ShuffleSchedulerImpl.java:306)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.copyFromHost(Fetcher.java:366)
        at org.apache.hadoop.mapreduce.task.reduce.Fetcher.run(Fetcher.java:198)

17/10/06 15:47:18 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000166_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_3 from host ip-172-31-35-178.us-east-2.compute.internal
17/10/06 15:47:18 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000161_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_3 from host ip-172-31-35-178.us-east-2.compute.internal
17/10/06 15:47:18 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000164_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_3 from host ip-172-31-35-178.us-east-2.compute.internal
17/10/06 15:47:18 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000162_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_3 from host ip-172-31-35-178.us-east-2.compute.internal
17/10/06 15:47:18 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000165_0, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_3 from host ip-172-31-35-178.us-east-2.compute.internal
17/10/06 15:47:18 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000013_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_3 from host ip-172-31-35-178.us-east-2.compute.internal
17/10/06 15:47:18 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000000_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_3 from host ip-172-31-35-178.us-east-2.compute.internal
17/10/06 15:47:18 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000001_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_3 from host ip-172-31-35-178.us-east-2.compute.internal
17/10/06 15:47:18 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000032_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_3 from host ip-172-31-35-178.us-east-2.compute.internal
17/10/06 15:47:18 INFO mapreduce.Job: Task Id : attempt_1507303969493_0003_m_000031_1, Status : FAILED
Too many fetch failures. Failing the attempt. Last failure reported by attempt_1507303969493_0003_r_000010_3 from host ip-172-31-35-178.us-east-2.compute.internal
17/10/06 15:47:18 INFO mapreduce.Job: Job job_1507303969493_0003 failed with state FAILED due to: Task failed task_1507303969493_0003_r_000010
Job failed as tasks failed. failedMaps:0 failedReduces:1

17/10/06 15:47:18 INFO mapreduce.Job: Counters: 41
        File System Counters
                FILE: Number of bytes read=20691
                FILE: Number of bytes written=2418548717
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=5519205821
                HDFS: Number of bytes written=0
                HDFS: Number of read operations=513
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=0
        Job Counters
                Failed map tasks=210
                Failed reduce tasks=35
                Killed map tasks=33
                Killed reduce tasks=11
                Launched map tasks=382
                Launched reduce tasks=42
                Other local map tasks=178
                Data-local map tasks=204
                Total time spent by all maps in occupied slots (ms)=5225494
                Total time spent by all reduces in occupied slots (ms)=454460
                Total time spent by all map tasks (ms)=5225494
                Total time spent by all reduce tasks (ms)=454460
                Total vcore-seconds taken by all map tasks=5225494
                Total vcore-seconds taken by all reduce tasks=454460
                Total megabyte-seconds taken by all map tasks=5350905856
                Total megabyte-seconds taken by all reduce tasks=465367040
        Map-Reduce Framework
                Map input records=55191800
                Map output records=55191800
                Map output bytes=5629563600
                Map output materialized bytes=2396981253
                Input split bytes=25821
                Combine input records=0
                Spilled Records=55191800
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=17638
                CPU time spent (ms)=586480
                Physical memory (bytes) snapshot=89538580480
                Virtual memory (bytes) snapshot=272314208256
                Total committed heap usage (bytes)=93969711104
        File Input Format Counters
                Bytes Read=5519180000
17/10/06 15:47:18 INFO terasort.TeraSort: done

real    4m56.928s
user    0m7.494s
sys     0m0.310s
```