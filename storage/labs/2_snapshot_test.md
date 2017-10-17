# Snapshot

## Copy to HDFS the zip file

```
[root@ip-172-32-9-69 ~]# sudo -u hdfs hdfs dfs -mkdir /user/andrasmakoviczki/precious
[root@ip-172-32-9-69 ~]# sudo -u hdfs hdfs dfs -put /tmp/SEBC-master.zip /user/andrasmakoviczki/precious/
```

## Create snapshot on directory
```
[root@ip-172-32-9-69 ~]# sudo -u hdfs hdfs dfsadmin -allowSnapshot /user/andrasmakoviczki/precious/
```

```
Allowing snaphot on /user/andrasmakoviczki/precious/ succeeded
```

```
[root@ip-172-32-9-69 ~]# sudo -u hdfs hdfs dfs -createSnapshot /user/andrasmakoviczki/precious/ sebc-hdfs-test
```

```
Created snapshot /user/andrasmakoviczki/precious/.snapshot/sebc-hdfs-test
```

## Delete the directory
```
[root@ip-172-32-9-69 ~]# sudo -u hdfs hdfs dfs -rm -r /user/andrasmakoviczki/precious/
```

```
rm: Failed to move to trash: hdfs://ip-172-32-4-188.eu-central-1.compute.internal:8020/user/andrasmakoviczki/precious: The directory /user/andrasmakoviczki/precious cannot be deleted since /user/andrasmakoviczki/precious is snapshottable and already has snapshots
```

## Delete the file

```
[root@ip-172-32-9-69 ~]# sudo -u hdfs hdfs dfs -rm -r /user/andrasmakoviczki/precious/SEBC-master.zip
```

```
17/10/17 12:01:51 INFO fs.TrashPolicyDefault: Moved: 'hdfs://ip-172-32-4-188.eu-central-1.compute.internal:8020/user/andrasmakoviczki/precious/SEBC-master.zip' to trash at: hdfs://ip-172-32-4-188.eu-central-1.compute.internal:8020/user/hdfs/.Trash/Current/user/andrasmakoviczki/precious/SEBC-master.zip
```

## Restore the file

```
[root@ip-172-32-9-69 ~]# sudo -u hdfs hdfs dfs -cp /user/andrasmakoviczki/precious/.snapshot/sebc-hdfs-test/SEBC-master.zip /user/andrasmakoviczki/precious/
[root@ip-172-32-9-69 ~]# sudo -u hdfs hdfs dfs -ls /user/andrasmakoviczki/precious/
```

```
Found 1 items
-rw-r--r--   3 hdfs andrasmakoviczki     450893 2017-10-17 12:08 /user/andrasmakoviczki/precious/SEBC-master.zip
```

