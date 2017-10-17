# Output of teragen
```
[root@ip-172-32-9-69 ~]# sudo -u hdfs time hadoop jar /opt/cloudera/parcels/CDH/jars/hadoop-examples.jar teragen -Dmapreduce.job.maps=4 -Dmapreduce.map.speculative=false -Ddfs.blocksize=32M 107374182 /user/andrasmakoviczki/ex2_andrasmakoviczki_teragen
```

```
17/10/17 09:29:24 INFO client.RMProxy: Connecting to ResourceManager at ip-172-32-0-33.eu-central-1.compute.internal/172.32.0.33:8032
17/10/17 09:29:25 INFO terasort.TeraSort: Generating 107374182 using 4
17/10/17 09:29:25 INFO mapreduce.JobSubmitter: number of splits:4
17/10/17 09:29:25 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1508192767318_0009
17/10/17 09:29:25 INFO impl.YarnClientImpl: Submitted application application_1508192767318_0009
17/10/17 09:29:25 INFO mapreduce.Job: The url to track the job: http://ip-172-32-0-33.eu-central-1.compute.internal:8088/proxy/application_1508192767318_0009/
17/10/17 09:29:25 INFO mapreduce.Job: Running job: job_1508192767318_0009
17/10/17 09:29:30 INFO mapreduce.Job: Job job_1508192767318_0009 running in uber mode : false
17/10/17 09:29:30 INFO mapreduce.Job:  map 0% reduce 0%
17/10/17 09:29:41 INFO mapreduce.Job:  map 12% reduce 0%
...
17/10/17 09:31:28 INFO mapreduce.Job:  map 100% reduce 0%
17/10/17 09:31:28 INFO mapreduce.Job: Job job_1508192767318_0009 completed successfully
17/10/17 09:31:28 INFO mapreduce.Job: Counters: 31
        File System Counters
                FILE: Number of bytes read=0
                FILE: Number of bytes written=488556
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=344
                HDFS: Number of bytes written=10737418200
                HDFS: Number of read operations=16
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=8
        Job Counters
                Launched map tasks=4
                Other local map tasks=4
                Total time spent by all maps in occupied slots (ms)=446283
                Total time spent by all reduces in occupied slots (ms)=0
                Total time spent by all map tasks (ms)=446283
                Total vcore-seconds taken by all map tasks=446283
                Total megabyte-seconds taken by all map tasks=456993792
        Map-Reduce Framework
                Map input records=107374182
                Map output records=107374182
                Input split bytes=344
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=1520
                CPU time spent (ms)=157460
                Physical memory (bytes) snapshot=841437184
                Virtual memory (bytes) snapshot=6255308800
                Total committed heap usage (bytes)=881328128
        org.apache.hadoop.examples.terasort.TeraGen$Counters
                CHECKSUM=230593859918397906
        File Input Format Counters
                Bytes Read=0
        File Output Format Counters
                Bytes Written=10737418200
```

```
5.70user 0.28system 2:06.36elapsed 4%CPU (0avgtext+0avgdata 180072maxresident)k
0inputs+1216outputs (0major+36405minor)pagefaults 0swaps
```

# Output of terasort

```
[root@ip-172-32-9-69 ~]# sudo -u hdfs time hadoop jar /opt/cloudera/parcels/CDH/jars/hadoop-examples.jar terasort /user/andrasmakoviczki/ex2_andrasmakoviczki_teragen /user/andrasmakoviczki/ex2_andrasmakoviczki_terasort
```

```
17/10/17 09:31:34 INFO terasort.TeraSort: starting
17/10/17 09:31:36 INFO input.FileInputFormat: Total input paths to process : 4
Spent 317ms computing base-splits.
Spent 8ms computing TeraScheduler splits.
Computing input splits took 325ms
Sampling 10 splits of 320
Making 8 from 100000 sampled records
Computing parititions took 1089ms
Spent 1417ms computing partitions.
17/10/17 09:31:37 INFO client.RMProxy: Connecting to ResourceManager at ip-172-32-0-33.eu-central-1.compute.internal/172.32.0.33:8032
17/10/17 09:31:38 INFO mapreduce.JobSubmitter: number of splits:320
17/10/17 09:31:38 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1508192767318_0010
17/10/17 09:31:38 INFO impl.YarnClientImpl: Submitted application application_1508192767318_0010
17/10/17 09:31:38 INFO mapreduce.Job: The url to track the job: http://ip-172-32-0-33.eu-central-1.compute.internal:8088/proxy/application_1508192767318_0010/
17/10/17 09:31:38 INFO mapreduce.Job: Running job: job_1508192767318_0010
17/10/17 09:31:44 INFO mapreduce.Job: Job job_1508192767318_0010 running in uber mode : false
17/10/17 09:31:44 INFO mapreduce.Job:  map 0% reduce 0%
17/10/17 09:31:52 INFO mapreduce.Job:  map 1% reduce 0%
...
17/10/17 09:38:21 INFO mapreduce.Job:  map 100% reduce 99%
17/10/17 09:38:22 INFO mapreduce.Job:  map 100% reduce 100%
17/10/17 09:38:22 INFO mapreduce.Job: Job job_1508192767318_0010 completed successfully
17/10/17 09:38:22 INFO mapreduce.Job: Counters: 50
        File System Counters
                FILE: Number of bytes read=4811937795
                FILE: Number of bytes written=9550111470
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=10737477400
                HDFS: Number of bytes written=10737418200
                HDFS: Number of read operations=984
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=16
        Job Counters
                Launched map tasks=320
                Launched reduce tasks=8
                Data-local map tasks=319
                Rack-local map tasks=1
                Total time spent by all maps in occupied slots (ms)=2210561
                Total time spent by all reduces in occupied slots (ms)=796472
                Total time spent by all map tasks (ms)=2210561
                Total time spent by all reduce tasks (ms)=796472
                Total vcore-seconds taken by all map tasks=2210561
                Total vcore-seconds taken by all reduce tasks=796472
                Total megabyte-seconds taken by all map tasks=2263614464
                Total megabyte-seconds taken by all reduce tasks=815587328
        Map-Reduce Framework
                Map input records=107374182
                Map output records=107374182
                Map output bytes=10952166564
                Map output materialized bytes=4697597105
                Input split bytes=59200
                Combine input records=0
                Combine output records=0
                Reduce input groups=107374182
                Reduce shuffle bytes=4697597105
                Reduce input records=107374182
                Reduce output records=107374182
                Spilled Records=214748364
                Shuffled Maps =2560
                Failed Shuffles=0
                Merged Map outputs=2560
                GC time elapsed (ms)=32044
                CPU time spent (ms)=1427220
                Physical memory (bytes) snapshot=157651320832
                Virtual memory (bytes) snapshot=514183454720
                Total committed heap usage (bytes)=186165755904
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
        File Input Format Counters
                Bytes Read=10737418200
        File Output Format Counters
                Bytes Written=10737418200
17/10/17 09:38:22 INFO terasort.TeraSort: done
```

```
10.56user 0.45system 6:48.55elapsed 2%CPU (0avgtext+0avgdata 193548maxresident)k
104inputs+1544outputs (1major+38599minor)pagefaults 0swaps
```

