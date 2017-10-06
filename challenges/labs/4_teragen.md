-Dmapred.map.tasks=12

```
[saturn@ip-172-31-35-215 tmp]$ time hadoop jar /disco1/cloudera/parcels/CDH/jars/hadoop-examples.jar teragen -Dmapred.map.tasks=12 -Ddfs.block.size=33554432 -Dmapreduce.map.memory.mb=512 65536000 /user/saturn/tgen2
17/10/06 15:03:09 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-35-215.us-east-2.compute.internal/172.31.35.215:8032
17/10/06 15:03:09 INFO terasort.TeraSort: Generating 65536000 using 12
17/10/06 15:03:09 INFO mapreduce.JobSubmitter: number of splits:12
17/10/06 15:03:09 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
17/10/06 15:03:09 INFO Configuration.deprecation: dfs.block.size is deprecated. Instead, use dfs.blocksize
17/10/06 15:03:10 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1507299537624_0001
17/10/06 15:03:10 INFO impl.YarnClientImpl: Submitted application application_1507299537624_0001
17/10/06 15:03:10 INFO mapreduce.Job: The url to track the job: http://ip-172-31-35-215.us-east-2.compute.internal:8088/proxy/application_1507299537624_0001/
17/10/06 15:03:10 INFO mapreduce.Job: Running job: job_1507299537624_0001
17/10/06 15:03:16 INFO mapreduce.Job: Job job_1507299537624_0001 running in uber mode : false
17/10/06 15:03:16 INFO mapreduce.Job:  map 0% reduce 0%
17/10/06 15:03:28 INFO mapreduce.Job:  map 6% reduce 0%
17/10/06 15:03:30 INFO mapreduce.Job:  map 17% reduce 0%
17/10/06 15:03:31 INFO mapreduce.Job:  map 19% reduce 0%
17/10/06 15:03:33 INFO mapreduce.Job:  map 24% reduce 0%
17/10/06 15:03:34 INFO mapreduce.Job:  map 26% reduce 0%
17/10/06 15:03:36 INFO mapreduce.Job:  map 31% reduce 0%
17/10/06 15:03:37 INFO mapreduce.Job:  map 34% reduce 0%
17/10/06 15:03:39 INFO mapreduce.Job:  map 39% reduce 0%
17/10/06 15:03:40 INFO mapreduce.Job:  map 41% reduce 0%
17/10/06 15:03:42 INFO mapreduce.Job:  map 46% reduce 0%
17/10/06 15:03:43 INFO mapreduce.Job:  map 48% reduce 0%
17/10/06 15:03:45 INFO mapreduce.Job:  map 51% reduce 0%
17/10/06 15:03:46 INFO mapreduce.Job:  map 54% reduce 0%
17/10/06 15:03:58 INFO mapreduce.Job:  map 60% reduce 0%
17/10/06 15:04:04 INFO mapreduce.Job:  map 66% reduce 0%
17/10/06 15:04:07 INFO mapreduce.Job:  map 67% reduce 0%
17/10/06 15:04:08 INFO mapreduce.Job:  map 68% reduce 0%
17/10/06 15:04:09 INFO mapreduce.Job:  map 74% reduce 0%
17/10/06 15:04:10 INFO mapreduce.Job:  map 79% reduce 0%
17/10/06 15:04:13 INFO mapreduce.Job:  map 82% reduce 0%
17/10/06 15:04:15 INFO mapreduce.Job:  map 88% reduce 0%
17/10/06 15:04:16 INFO mapreduce.Job:  map 89% reduce 0%
17/10/06 15:04:18 INFO mapreduce.Job:  map 94% reduce 0%
17/10/06 15:04:19 INFO mapreduce.Job:  map 95% reduce 0%
17/10/06 15:04:20 INFO mapreduce.Job:  map 96% reduce 0%
17/10/06 15:04:21 INFO mapreduce.Job:  map 99% reduce 0%
17/10/06 15:04:22 INFO mapreduce.Job:  map 100% reduce 0%
17/10/06 15:04:23 INFO mapreduce.Job: Job job_1507299537624_0001 completed successfully
17/10/06 15:04:23 INFO mapreduce.Job: Counters: 31
        File System Counters
                FILE: Number of bytes read=0
                FILE: Number of bytes written=1483934
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=1025
                HDFS: Number of bytes written=6553600000
                HDFS: Number of read operations=48
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=24
        Job Counters
                Launched map tasks=12
                Other local map tasks=12
                Total time spent by all maps in occupied slots (ms)=712916
                Total time spent by all reduces in occupied slots (ms)=0
                Total time spent by all map tasks (ms)=712916
                Total vcore-seconds taken by all map tasks=712916
                Total megabyte-seconds taken by all map tasks=730025984
        Map-Reduce Framework
                Map input records=65536000
                Map output records=65536000
                Input split bytes=1025
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=2736
                CPU time spent (ms)=134930
                Physical memory (bytes) snapshot=2415689728
                Virtual memory (bytes) snapshot=13771198464
                Total committed heap usage (bytes)=4447535104
        org.apache.hadoop.examples.terasort.TeraGen$Counters
                CHECKSUM=140750829423462787
        File Input Format Counters
                Bytes Read=0
        File Output Format Counters
                Bytes Written=6553600000

real    1m16.469s
user    0m4.466s
sys     0m0.295s
```

```
[saturn@ip-172-31-35-215 tmp]$ hdfs dfs -ls /user/saturn/tgen2
Found 13 items
-rw-r--r--   3 saturn planets          0 2017-10-06 15:04 /user/saturn/tgen2/_SUCCESS
-rw-r--r--   3 saturn planets  546133400 2017-10-06 15:04 /user/saturn/tgen2/part-m-00000
-rw-r--r--   3 saturn planets  546133300 2017-10-06 15:04 /user/saturn/tgen2/part-m-00001
-rw-r--r--   3 saturn planets  546133300 2017-10-06 15:04 /user/saturn/tgen2/part-m-00002
-rw-r--r--   3 saturn planets  546133400 2017-10-06 15:04 /user/saturn/tgen2/part-m-00003
-rw-r--r--   3 saturn planets  546133300 2017-10-06 15:04 /user/saturn/tgen2/part-m-00004
-rw-r--r--   3 saturn planets  546133300 2017-10-06 15:04 /user/saturn/tgen2/part-m-00005
-rw-r--r--   3 saturn planets  546133400 2017-10-06 15:04 /user/saturn/tgen2/part-m-00006
-rw-r--r--   3 saturn planets  546133300 2017-10-06 15:04 /user/saturn/tgen2/part-m-00007
-rw-r--r--   3 saturn planets  546133300 2017-10-06 15:04 /user/saturn/tgen2/part-m-00008
-rw-r--r--   3 saturn planets  546133400 2017-10-06 15:04 /user/saturn/tgen2/part-m-00009
-rw-r--r--   3 saturn planets  546133300 2017-10-06 15:04 /user/saturn/tgen2/part-m-00010
-rw-r--r--   3 saturn planets  546133300 2017-10-06 15:04 /user/saturn/tgen2/part-m-00011
```

```
[saturn@ip-172-31-35-215 tmp]$ hadoop fsck -blocks /user/saturn
DEPRECATED: Use of this script to execute hdfs command is deprecated.
Instead use the hdfs command for it.

Connecting to namenode via http://ip-172-31-33-183.us-east-2.compute.internal:50070
FSCK started by saturn (auth:SIMPLE) from /172.31.35.215 for path /user/saturn at Fri Oct 06 15:06:30 UTC 2017
.........................Status: HEALTHY
 Total size:    45875200000 B
 Total dirs:    17
 Total files:   25
 Total symlinks:                0
 Total blocks (validated):      1380 (avg. block size 33242898 B)
 Minimally replicated blocks:   1380 (100.0 %)
 Over-replicated blocks:        0 (0.0 %)
 Under-replicated blocks:       0 (0.0 %)
 Mis-replicated blocks:         0 (0.0 %)
 Default replication factor:    3
 Average block replication:     3.0
 Corrupt blocks:                0
 Missing replicas:              0 (0.0 %)
 Number of data-nodes:          3
 Number of racks:               1
FSCK ended at Fri Oct 06 15:06:30 UTC 2017 in 53 milliseconds


The filesystem under path '/user/saturn' is HEALTHY

```
