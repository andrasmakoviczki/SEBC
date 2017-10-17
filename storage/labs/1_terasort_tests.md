# Output of teragen
```
[root@ip-172-32-9-69 ~]# sudo -u hdfs time hadoop jar /opt/cloudera/parcels/CDH/jars/hadoop-examples.jar teragen -Dmapreduce.job.maps=4 -Dmapreduce.map.speculative=false -Ddfs.blocksize=32M 107374182 /user/andrasmakoviczki/ex2_andrasmakoviczki_teragen
```

```
17/10/17 09:16:48 INFO client.RMProxy: Connecting to ResourceManager at ip-172-32-0-33.eu-central-1.compute.internal/172.32.0.33:8032
17/10/17 09:16:50 INFO terasort.TeraSort: Generating 107374182 using 4
17/10/17 09:16:51 INFO mapreduce.JobSubmitter: number of splits:4
17/10/17 09:16:52 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1508192767318_0007
17/10/17 09:16:52 INFO impl.YarnClientImpl: Submitted application application_1508192767318_0007
17/10/17 09:16:53 INFO mapreduce.Job: The url to track the job: http://ip-172-32-0-33.eu-central-1.compute.internal:8088/proxy/application_1508192767318_0007/
17/10/17 09:16:53 INFO mapreduce.Job: Running job: job_1508192767318_0007
17/10/17 09:17:01 INFO mapreduce.Job: Job job_1508192767318_0007 running in uber mode : false
17/10/17 09:17:01 INFO mapreduce.Job:  map 0% reduce 0%
17/10/17 09:17:12 INFO mapreduce.Job:  map 1% reduce 0%
...
17/10/17 09:20:37 INFO mapreduce.Job:  map 100% reduce 0%
17/10/17 09:20:38 INFO mapreduce.Job: Job job_1508192767318_0007 completed successfully
17/10/17 09:20:38 INFO mapreduce.Job: Counters: 32
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
                Failed map tasks=4
                Launched map tasks=8
                Other local map tasks=8
                Total time spent by all maps in occupied slots (ms)=843922
                Total time spent by all reduces in occupied slots (ms)=0
                Total time spent by all map tasks (ms)=843922
                Total vcore-seconds taken by all map tasks=843922
                Total megabyte-seconds taken by all map tasks=864176128
        Map-Reduce Framework
                Map input records=107374182
                Map output records=107374182
                Input split bytes=344
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=1647
                CPU time spent (ms)=157070
                Physical memory (bytes) snapshot=757432320
                Virtual memory (bytes) snapshot=6260023296
                Total committed heap usage (bytes)=832569344
        org.apache.hadoop.examples.terasort.TeraGen$Counters
                CHECKSUM=230593859918397906
        File Input Format Counters
                Bytes Read=0
        File Output Format Counters
                Bytes Written=10737418200
```

```			
7.52user 0.93system 3:53.53elapsed 3%CPU (0avgtext+0avgdata 234016maxresident)k
80inputs+205000outputs (0major+43573minor)pagefaults 0swaps
```
