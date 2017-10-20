# Command and output of pi

```
[siwicki@ip-172-32-7-232 ~]$ yarn jar /opt/cloudera/parcels/CDH/jars/hadoop-examples.jar pi 10 100
```

```
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
17/10/20 09:38:14 INFO client.RMProxy: Connecting to ResourceManager at ip-172-32-7-232.eu-central-1.compute.internal/172.32.7.232:8032
17/10/20 09:38:14 INFO hdfs.DFSClient: Created token for siwicki: HDFS_DELEGATION_TOKEN owner=siwicki@ANDRASMAKOVICZKI.CO.UK, renewer=yarn, realUser=, issueDate=1508492294991, maxDate=1509097094991, sequenceNumber=3, masterKeyId=2 on 172.32.7.232:8020
17/10/20 09:38:15 INFO security.TokenCache: Got dt for hdfs://ip-172-32-7-232.eu-central-1.compute.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.32.7.232:8020, Ident: (token for siwicki: HDFS_DELEGATION_TOKEN owner=siwicki@ANDRASMAKOVICZKI.CO.UK, renewer=yarn, realUser=, issueDate=1508492294991, maxDate=1509097094991, sequenceNumber=3, masterKeyId=2)
17/10/20 09:38:15 INFO input.FileInputFormat: Total input paths to process : 10
17/10/20 09:38:15 INFO mapreduce.JobSubmitter: number of splits:10
17/10/20 09:38:15 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1508491549679_0003
17/10/20 09:38:15 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.32.7.232:8020, Ident: (token for siwicki: HDFS_DELEGATION_TOKEN owner=siwicki@ANDRASMAKOVICZKI.CO.UK, renewer=yarn, realUser=, issueDate=1508492294991, maxDate=1509097094991, sequenceNumber=3, masterKeyId=2)
17/10/20 09:38:15 INFO impl.YarnClientImpl: Submitted application application_1508491549679_0003
17/10/20 09:38:15 INFO mapreduce.Job: The url to track the job: http://ip-172-32-7-232.eu-central-1.compute.internal:8088/proxy/application_1508491549679_0003/
17/10/20 09:38:15 INFO mapreduce.Job: Running job: job_1508491549679_0003
17/10/20 09:38:25 INFO mapreduce.Job: Job job_1508491549679_0003 running in uber mode : false
17/10/20 09:38:25 INFO mapreduce.Job:  map 0% reduce 0%
17/10/20 09:38:34 INFO mapreduce.Job:  map 20% reduce 0%
17/10/20 09:38:36 INFO mapreduce.Job:  map 30% reduce 0%
17/10/20 09:38:37 INFO mapreduce.Job:  map 60% reduce 0%
17/10/20 09:38:39 INFO mapreduce.Job:  map 100% reduce 0%
17/10/20 09:38:45 INFO mapreduce.Job:  map 100% reduce 100%
17/10/20 09:38:46 INFO mapreduce.Job: Job job_1508491549679_0003 completed successfully
17/10/20 09:38:46 INFO mapreduce.Job: Counters: 50
        File System Counters
         FILE: Number of bytes read=96
         FILE: Number of bytes written=1376305
         FILE: Number of read operations=0
         FILE: Number of large read operations=0
         FILE: Number of write operations=0
         HDFS: Number of bytes read=3020
         HDFS: Number of bytes written=215
         HDFS: Number of read operations=43
         HDFS: Number of large read operations=0
         HDFS: Number of write operations=3
        Job Counters
         Launched map tasks=10
         Launched reduce tasks=1
         Data-local map tasks=8
         Rack-local map tasks=2
         Total time spent by all maps in occupied slots (ms)=93200
         Total time spent by all reduces in occupied slots (ms)=3728
         Total time spent by all map tasks (ms)=93200
         Total time spent by all reduce tasks (ms)=3728
         Total vcore-seconds taken by all map tasks=93200
         Total vcore-seconds taken by all reduce tasks=3728
         Total megabyte-seconds taken by all map tasks=95436800
         Total megabyte-seconds taken by all reduce tasks=3817472
        Map-Reduce Framework
         Map input records=10
         Map output records=20
         Map output bytes=180
         Map output materialized bytes=340
         Input split bytes=1840
         Combine input records=0
         Combine output records=0
         Reduce input groups=2
         Reduce shuffle bytes=340
         Reduce input records=20
         Reduce output records=0
         Spilled Records=40
         Shuffled Maps =10
         Failed Shuffles=0
         Merged Map outputs=10
         GC time elapsed (ms)=1120
         CPU time spent (ms)=8310
         Physical memory (bytes) snapshot=4596158464
         Virtual memory (bytes) snapshot=30472151040
         Total committed heap usage (bytes)=4623171584
        Shuffle Errors
         BAD_ID=0
         CONNECTION=0
         IO_ERROR=0
         WRONG_LENGTH=0
         WRONG_MAP=0
         WRONG_REDUCE=0
        File Input Format Counters
         Bytes Read=1180
        File Output Format Counters
         Bytes Written=97
Job Finished in 31.639 seconds
Estimated value of Pi is 3.14800000000000000000
```