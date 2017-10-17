# Source directory check
```
[root@ip-172-32-9-69 ~]# sudo -u hdfs hdfs fsck /user/andrasmakoviczki/ex1_andrasmakoviczki_source -files -blocks 
```

```
Connecting to namenode via http://ip-172-32-0-33.eu-central-1.compute.internal:50070
FSCK started by hdfs (auth:SIMPLE) from /172.32.9.69 for path /user/andrasmakoviczki/ex1_andrasmakoviczki_source at Tue Oct 17 09:03:07 UTC 2017
/user/andrasmakoviczki/ex1_andrasmakoviczki_source <dir>
/user/andrasmakoviczki/ex1_andrasmakoviczki_source/_SUCCESS 0 bytes, 0 block(s):  OK

/user/andrasmakoviczki/ex1_andrasmakoviczki_source/part-m-00000 262144000 bytes, 2 block(s):  OK
0. BP-1927535081-172.32.0.33-1508192706530:blk_1073744082_3258 len=134217728 Live_repl=3
1. BP-1927535081-172.32.0.33-1508192706530:blk_1073744084_3260 len=127926272 Live_repl=3

/user/andrasmakoviczki/ex1_andrasmakoviczki_source/part-m-00001 262144000 bytes, 2 block(s):  OK
0. BP-1927535081-172.32.0.33-1508192706530:blk_1073744081_3257 len=134217728 Live_repl=3
1. BP-1927535081-172.32.0.33-1508192706530:blk_1073744083_3259 len=127926272 Live_repl=3

Status: HEALTHY
 Total size:    524288000 B
 Total dirs:    1
 Total files:   3
 Total symlinks:                0
 Total blocks (validated):      4 (avg. block size 131072000 B)
 Minimally replicated blocks:   4 (100.0 %)
 Over-replicated blocks:        0 (0.0 %)
 Under-replicated blocks:       0 (0.0 %)
 Mis-replicated blocks:         0 (0.0 %)
 Default replication factor:    3
 Average block replication:     3.0
 Corrupt blocks:                0
 Missing replicas:              0 (0.0 %)
 Number of data-nodes:          4
 Number of racks:               1
FSCK ended at Tue Oct 17 09:03:07 UTC 2017 in 1 milliseconds


The filesystem under path '/user/andrasmakoviczki/ex1_andrasmakoviczki_source' is HEALTHY
```

# Target directory check

```
[root@ip-172-32-9-69 ~]# sudo -u hdfs hdfs fsck /user/andrasmakoviczki/ex1_zoltankis_target -files -blocks
```

```
Connecting to namenode via http://ip-172-32-0-33.eu-central-1.compute.internal:50070
FSCK started by hdfs (auth:SIMPLE) from /172.32.9.69 for path /user/andrasmakoviczki/ex1_zoltankis_target at Tue Oct 17 09:04:47 UTC 2017
/user/andrasmakoviczki/ex1_zoltankis_target <dir>
/user/andrasmakoviczki/ex1_zoltankis_target/_SUCCESS 0 bytes, 0 block(s):  OK

/user/andrasmakoviczki/ex1_zoltankis_target/part-m-00000 524288000 bytes, 4 block(s):  OK
0. BP-1927535081-172.32.0.33-1508192706530:blk_1073743829_3005 len=134217728 Live_repl=3
1. BP-1927535081-172.32.0.33-1508192706530:blk_1073743835_3011 len=134217728 Live_repl=3
2. BP-1927535081-172.32.0.33-1508192706530:blk_1073743838_3014 len=134217728 Live_repl=3
3. BP-1927535081-172.32.0.33-1508192706530:blk_1073743842_3018 len=121634816 Live_repl=3

Status: HEALTHY
 Total size:    524288000 B
 Total dirs:    1
 Total files:   2
 Total symlinks:                0
 Total blocks (validated):      4 (avg. block size 131072000 B)
 Minimally replicated blocks:   4 (100.0 %)
 Over-replicated blocks:        0 (0.0 %)
 Under-replicated blocks:       0 (0.0 %)
 Mis-replicated blocks:         0 (0.0 %)
 Default replication factor:    3
 Average block replication:     3.0
 Corrupt blocks:                0
 Missing replicas:              0 (0.0 %)
 Number of data-nodes:          4
 Number of racks:               1
FSCK ended at Tue Oct 17 09:04:47 UTC 2017 in 1 milliseconds


The filesystem under path '/user/andrasmakoviczki/ex1_zoltankis_target' is HEALTHY
```