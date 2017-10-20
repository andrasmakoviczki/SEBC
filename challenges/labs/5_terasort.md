# Command and output of terasort

```
[ernest@ip-172-32-7-232 ~]$ yarn jar /opt/cloudera/parcels/CDH/jars/hadoop-examples.jar terasort /user/ernest/tgen512m /user/ernest/tsort512m
```

```
17/10/20 09:28:42 INFO terasort.TeraSort: starting
17/10/20 09:28:44 INFO hdfs.DFSClient: Created token for ernest: HDFS_DELEGATION_TOKEN owner=ernest@ANDRASMAKOVICZKI.CO.UK, renewer=yarn, realUser=, issueDate=1508491724199, maxDate=1509096524199, sequenceNumber=1, masterKeyId=2 on 172.32.7.232:8020
17/10/20 09:28:44 INFO security.TokenCache: Got dt for hdfs://ip-172-32-7-232.eu-central-1.compute.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.32.7.232:8020, Ident: (token for ernest: HDFS_DELEGATION_TOKEN owner=ernest@ANDRASMAKOVICZKI.CO.UK, renewer=yarn, realUser=, issueDate=1508491724199, maxDate=1509096524199, sequenceNumber=1, masterKeyId=2)
17/10/20 09:28:44 INFO input.FileInputFormat: Total input paths to process : 6
Spent 405ms computing base-splits.
Spent 4ms computing TeraScheduler splits.
Computing input splits took 409ms
Sampling 10 splits of 156
Making 8 from 100000 sampled records
Computing parititions took 774ms
Spent 1186ms computing partitions.
17/10/20 09:28:45 INFO client.RMProxy: Connecting to ResourceManager at ip-172-32-7-232.eu-central-1.compute.internal/172.32.7.232:8032
17/10/20 09:28:45 INFO mapreduce.JobSubmitter: number of splits:156
17/10/20 09:28:45 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1508491549679_0001
17/10/20 09:28:45 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.32.7.232:8020, Ident: (token for ernest: HDFS_DELEGATION_TOKEN owner=ernest@ANDRASMAKOVICZKI.CO.UK, renewer=yarn, realUser=, issueDate=1508491724199, maxDate=1509096524199, sequenceNumber=1, masterKeyId=2)
17/10/20 09:28:46 INFO impl.YarnClientImpl: Submitted application application_1508491549679_0001
17/10/20 09:28:46 INFO mapreduce.Job: The url to track the job: http://ip-172-32-7-232.eu-central-1.compute.internal:8088/proxy/application_1508491549679_0001/
17/10/20 09:28:46 INFO mapreduce.Job: Running job: job_1508491549679_0001
17/10/20 09:28:56 INFO mapreduce.Job: Job job_1508491549679_0001 running in uber mode : false
17/10/20 09:28:56 INFO mapreduce.Job:  map 0% reduce 0%
17/10/20 09:29:04 INFO mapreduce.Job:  map 1% reduce 0%
17/10/20 09:29:06 INFO mapreduce.Job:  map 2% reduce 0%
17/10/20 09:29:08 INFO mapreduce.Job:  map 3% reduce 0%
17/10/20 09:29:11 INFO mapreduce.Job:  map 4% reduce 0%
17/10/20 09:29:12 INFO mapreduce.Job:  map 5% reduce 0%
17/10/20 09:29:14 INFO mapreduce.Job:  map 8% reduce 0%
17/10/20 09:29:15 INFO mapreduce.Job:  map 9% reduce 0%
17/10/20 09:29:17 INFO mapreduce.Job:  map 10% reduce 0%
17/10/20 09:29:18 INFO mapreduce.Job:  map 11% reduce 0%
17/10/20 09:29:22 INFO mapreduce.Job:  map 12% reduce 0%
17/10/20 09:29:23 INFO mapreduce.Job:  map 13% reduce 0%
17/10/20 09:29:24 INFO mapreduce.Job:  map 14% reduce 0%
17/10/20 09:29:26 INFO mapreduce.Job:  map 17% reduce 0%
17/10/20 09:29:28 INFO mapreduce.Job:  map 19% reduce 0%
17/10/20 09:29:32 INFO mapreduce.Job:  map 20% reduce 0%
17/10/20 09:29:33 INFO mapreduce.Job:  map 21% reduce 0%
17/10/20 09:29:35 INFO mapreduce.Job:  map 22% reduce 0%
17/10/20 09:29:37 INFO mapreduce.Job:  map 24% reduce 0%
17/10/20 09:29:38 INFO mapreduce.Job:  map 25% reduce 0%
17/10/20 09:29:39 INFO mapreduce.Job:  map 26% reduce 0%
17/10/20 09:29:42 INFO mapreduce.Job:  map 27% reduce 0%
17/10/20 09:29:43 INFO mapreduce.Job:  map 28% reduce 0%
17/10/20 09:29:45 INFO mapreduce.Job:  map 29% reduce 0%
17/10/20 09:29:48 INFO mapreduce.Job:  map 31% reduce 0%
17/10/20 09:29:49 INFO mapreduce.Job:  map 33% reduce 0%
17/10/20 09:29:50 INFO mapreduce.Job:  map 34% reduce 0%
17/10/20 09:29:52 INFO mapreduce.Job:  map 35% reduce 0%
17/10/20 09:29:54 INFO mapreduce.Job:  map 36% reduce 0%
17/10/20 09:29:55 INFO mapreduce.Job:  map 37% reduce 0%
17/10/20 09:29:58 INFO mapreduce.Job:  map 38% reduce 0%
17/10/20 09:29:59 INFO mapreduce.Job:  map 40% reduce 0%
17/10/20 09:30:00 INFO mapreduce.Job:  map 42% reduce 0%
17/10/20 09:30:01 INFO mapreduce.Job:  map 43% reduce 0%
17/10/20 09:30:06 INFO mapreduce.Job:  map 46% reduce 0%
17/10/20 09:30:10 INFO mapreduce.Job:  map 47% reduce 0%
17/10/20 09:30:11 INFO mapreduce.Job:  map 49% reduce 0%
17/10/20 09:30:13 INFO mapreduce.Job:  map 51% reduce 0%
17/10/20 09:30:14 INFO mapreduce.Job:  map 52% reduce 0%
17/10/20 09:30:17 INFO mapreduce.Job:  map 53% reduce 0%
17/10/20 09:30:20 INFO mapreduce.Job:  map 55% reduce 0%
17/10/20 09:30:21 INFO mapreduce.Job:  map 57% reduce 0%
17/10/20 09:30:22 INFO mapreduce.Job:  map 58% reduce 0%
17/10/20 09:30:25 INFO mapreduce.Job:  map 59% reduce 0%
17/10/20 09:30:26 INFO mapreduce.Job:  map 60% reduce 0%
17/10/20 09:30:27 INFO mapreduce.Job:  map 62% reduce 0%
17/10/20 09:30:31 INFO mapreduce.Job:  map 63% reduce 0%
17/10/20 09:30:32 INFO mapreduce.Job:  map 65% reduce 0%
17/10/20 09:30:33 INFO mapreduce.Job:  map 66% reduce 0%
17/10/20 09:30:34 INFO mapreduce.Job:  map 67% reduce 0%
17/10/20 09:30:38 INFO mapreduce.Job:  map 69% reduce 0%
17/10/20 09:30:41 INFO mapreduce.Job:  map 70% reduce 0%
17/10/20 09:30:42 INFO mapreduce.Job:  map 71% reduce 0%
17/10/20 09:30:43 INFO mapreduce.Job:  map 72% reduce 0%
17/10/20 09:30:44 INFO mapreduce.Job:  map 74% reduce 0%
17/10/20 09:30:45 INFO mapreduce.Job:  map 75% reduce 0%
17/10/20 09:30:48 INFO mapreduce.Job:  map 76% reduce 0%
17/10/20 09:30:49 INFO mapreduce.Job:  map 77% reduce 0%
17/10/20 09:30:52 INFO mapreduce.Job:  map 78% reduce 0%
17/10/20 09:30:54 INFO mapreduce.Job:  map 81% reduce 0%
17/10/20 09:30:55 INFO mapreduce.Job:  map 82% reduce 0%
17/10/20 09:30:56 INFO mapreduce.Job:  map 83% reduce 0%
17/10/20 09:30:59 INFO mapreduce.Job:  map 85% reduce 0%
17/10/20 09:31:01 INFO mapreduce.Job:  map 86% reduce 0%
17/10/20 09:31:05 INFO mapreduce.Job:  map 87% reduce 0%
17/10/20 09:31:06 INFO mapreduce.Job:  map 88% reduce 0%
17/10/20 09:31:07 INFO mapreduce.Job:  map 89% reduce 0%
17/10/20 09:31:09 INFO mapreduce.Job:  map 89% reduce 3%
17/10/20 09:31:10 INFO mapreduce.Job:  map 89% reduce 7%
17/10/20 09:31:11 INFO mapreduce.Job:  map 90% reduce 14%
17/10/20 09:31:12 INFO mapreduce.Job:  map 90% reduce 15%
17/10/20 09:31:15 INFO mapreduce.Job:  map 90% reduce 19%
17/10/20 09:31:16 INFO mapreduce.Job:  map 92% reduce 19%
17/10/20 09:31:22 INFO mapreduce.Job:  map 93% reduce 19%
17/10/20 09:31:23 INFO mapreduce.Job:  map 94% reduce 19%
17/10/20 09:31:26 INFO mapreduce.Job:  map 95% reduce 20%
17/10/20 09:31:27 INFO mapreduce.Job:  map 96% reduce 20%
17/10/20 09:31:31 INFO mapreduce.Job:  map 97% reduce 20%
17/10/20 09:31:33 INFO mapreduce.Job:  map 98% reduce 20%
17/10/20 09:31:37 INFO mapreduce.Job:  map 99% reduce 20%
17/10/20 09:31:38 INFO mapreduce.Job:  map 100% reduce 20%
17/10/20 09:31:39 INFO mapreduce.Job:  map 100% reduce 22%
17/10/20 09:31:40 INFO mapreduce.Job:  map 100% reduce 23%
17/10/20 09:31:41 INFO mapreduce.Job:  map 100% reduce 32%
17/10/20 09:31:42 INFO mapreduce.Job:  map 100% reduce 38%
17/10/20 09:31:43 INFO mapreduce.Job:  map 100% reduce 41%
17/10/20 09:31:44 INFO mapreduce.Job:  map 100% reduce 43%
17/10/20 09:31:45 INFO mapreduce.Job:  map 100% reduce 44%
17/10/20 09:31:46 INFO mapreduce.Job:  map 100% reduce 49%
17/10/20 09:31:47 INFO mapreduce.Job:  map 100% reduce 51%
17/10/20 09:31:48 INFO mapreduce.Job:  map 100% reduce 56%
17/10/20 09:31:49 INFO mapreduce.Job:  map 100% reduce 62%
17/10/20 09:31:50 INFO mapreduce.Job:  map 100% reduce 66%
17/10/20 09:31:51 INFO mapreduce.Job:  map 100% reduce 73%
17/10/20 09:31:52 INFO mapreduce.Job:  map 100% reduce 82%
17/10/20 09:31:53 INFO mapreduce.Job:  map 100% reduce 83%
17/10/20 09:31:54 INFO mapreduce.Job:  map 100% reduce 84%
17/10/20 09:31:55 INFO mapreduce.Job:  map 100% reduce 87%
17/10/20 09:31:57 INFO mapreduce.Job:  map 100% reduce 89%
17/10/20 09:31:58 INFO mapreduce.Job:  map 100% reduce 91%
17/10/20 09:32:00 INFO mapreduce.Job:  map 100% reduce 93%
17/10/20 09:32:01 INFO mapreduce.Job:  map 100% reduce 96%
17/10/20 09:32:04 INFO mapreduce.Job:  map 100% reduce 99%
17/10/20 09:32:06 INFO mapreduce.Job:  map 100% reduce 100%
17/10/20 09:32:06 INFO mapreduce.Job: Job job_1508491549679_0001 completed successfully
17/10/20 09:32:06 INFO mapreduce.Job: Counters: 49
        File System Counters
         FILE: Number of bytes read=2285967449
         FILE: Number of bytes written=4546711581
         FILE: Number of read operations=0
         FILE: Number of large read operations=0
         FILE: Number of write operations=0
         HDFS: Number of bytes read=5120024336
         HDFS: Number of bytes written=5120000000
         HDFS: Number of read operations=492
         HDFS: Number of large read operations=0
         HDFS: Number of write operations=16
        Job Counters
         Launched map tasks=156
         Launched reduce tasks=8
         Data-local map tasks=156
         Total time spent by all maps in occupied slots (ms)=1084775
         Total time spent by all reduces in occupied slots (ms)=340844
         Total time spent by all map tasks (ms)=1084775
         Total time spent by all reduce tasks (ms)=340844
         Total vcore-seconds taken by all map tasks=1084775
         Total vcore-seconds taken by all reduce tasks=340844
         Total megabyte-seconds taken by all map tasks=1110809600
         Total megabyte-seconds taken by all reduce tasks=349024256
        Map-Reduce Framework
         Map input records=51200000
         Map output records=51200000
         Map output bytes=5222400000
         Map output materialized bytes=2240098318
         Input split bytes=24336
         Combine input records=0
         Combine output records=0
         Reduce input groups=51200000
         Reduce shuffle bytes=2240098318
         Reduce input records=51200000
         Reduce output records=51200000
         Spilled Records=102400000
         Shuffled Maps =1248
         Failed Shuffles=0
         Merged Map outputs=1248
         GC time elapsed (ms)=23180
         CPU time spent (ms)=780990
         Physical memory (bytes) snapshot=78920077312
         Virtual memory (bytes) snapshot=454560235520
         Total committed heap usage (bytes)=80481353728
        Shuffle Errors
         BAD_ID=0
         CONNECTION=0
         IO_ERROR=0
         WRONG_LENGTH=0
         WRONG_MAP=0
         WRONG_REDUCE=0
        File Input Format Counters
         Bytes Read=5120000000
        File Output Format Counters
         Bytes Written=5120000000
17/10/20 09:32:06 INFO terasort.TeraSort: done
```