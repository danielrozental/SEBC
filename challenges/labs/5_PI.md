```
[root@ip-172-31-33-183 yarn]# time hadoop jar /disco1/cloudera/parcels/CDH/jars/hadoop-examples.jar pi 4 100
Number of Maps  = 4
Samples per Map = 100
Wrote input for Map #0
Wrote input for Map #1
Wrote input for Map #2
Wrote input for Map #3
Starting Job
17/10/06 16:02:05 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-35-215.us-east-2.compute.internal/172.31.35.215:8032
17/10/06 16:02:05 INFO hdfs.DFSClient: Created token for haley: HDFS_DELEGATION_TOKEN owner=haley@DANIELROZENTAL.HQ, renewer=yarn, realUser=, issueDate=1507305725385, maxDate=1507910525385, sequenceNumber=6, masterKeyId=2 on 172.31.33.183:8020
17/10/06 16:02:05 INFO security.TokenCache: Got dt for hdfs://ip-172-31-33-183.us-east-2.compute.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.33.183:8020, Ident: (token for haley: HDFS_DELEGATION_TOKEN owner=haley@DANIELROZENTAL.HQ, renewer=yarn, realUser=, issueDate=1507305725385, maxDate=1507910525385, sequenceNumber=6, masterKeyId=2)
17/10/06 16:02:05 INFO input.FileInputFormat: Total input paths to process : 4
17/10/06 16:02:05 INFO mapreduce.JobSubmitter: number of splits:4
17/10/06 16:02:05 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1507303969493_0006
17/10/06 16:02:05 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.33.183:8020, Ident: (token for haley: HDFS_DELEGATION_TOKEN owner=haley@DANIELROZENTAL.HQ, renewer=yarn, realUser=, issueDate=1507305725385, maxDate=1507910525385, sequenceNumber=6, masterKeyId=2)
17/10/06 16:02:06 INFO impl.YarnClientImpl: Submitted application application_1507303969493_0006
17/10/06 16:02:06 INFO mapreduce.Job: The url to track the job: http://ip-172-31-35-215.us-east-2.compute.internal:8088/proxy/application_1507303969493_0006/
17/10/06 16:02:06 INFO mapreduce.Job: Running job: job_1507303969493_0006
17/10/06 16:02:13 INFO mapreduce.Job: Job job_1507303969493_0006 running in uber mode : false
17/10/06 16:02:13 INFO mapreduce.Job:  map 0% reduce 0%
17/10/06 16:02:19 INFO mapreduce.Job:  map 100% reduce 0%
17/10/06 16:02:26 INFO mapreduce.Job:  map 100% reduce 100%
17/10/06 16:02:26 INFO mapreduce.Job: Job job_1507303969493_0006 completed successfully
17/10/06 16:02:26 INFO mapreduce.Job: Counters: 49
        File System Counters
                FILE: Number of bytes read=64
                FILE: Number of bytes written=625765
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=1196
                HDFS: Number of bytes written=215
                HDFS: Number of read operations=19
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=3
        Job Counters
                Launched map tasks=4
                Launched reduce tasks=1
                Data-local map tasks=4
                Total time spent by all maps in occupied slots (ms)=16363
                Total time spent by all reduces in occupied slots (ms)=4467
                Total time spent by all map tasks (ms)=16363
                Total time spent by all reduce tasks (ms)=4467
                Total vcore-seconds taken by all map tasks=16363
                Total vcore-seconds taken by all reduce tasks=4467
                Total megabyte-seconds taken by all map tasks=16755712
                Total megabyte-seconds taken by all reduce tasks=4574208
        Map-Reduce Framework
                Map input records=4
                Map output records=8
                Map output bytes=72
                Map output materialized bytes=136
                Input split bytes=724
                Combine input records=0
                Combine output records=0
                Reduce input groups=2
                Reduce shuffle bytes=136
                Reduce input records=8
                Reduce output records=0
                Spilled Records=16
                Shuffled Maps =4
                Failed Shuffles=0
                Merged Map outputs=4
                GC time elapsed (ms)=111
                CPU time spent (ms)=2960
                Physical memory (bytes) snapshot=2315255808
                Virtual memory (bytes) snapshot=8032858112
                Total committed heap usage (bytes)=2492989440
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
        File Input Format Counters
                Bytes Read=472
        File Output Format Counters
                Bytes Written=97
Job Finished in 21.326 seconds
Estimated value of Pi is 3.17000000000000000000

real    0m23.672s
user    0m4.492s
sys     0m0.201s
```