# MySQL host

```
[root@ip-172-32-9-75 ~]# hostname -f
```

```
ip-172-32-9-75.eu-central-1.compute.internal
```

# MySQL version

```
[root@ip-172-32-9-75 ~]# mysql --version
```

```
mysql  Ver 14.14 Distrib 5.5.58, for Linux (x86_64) using readline 5.1
```

# Show databases

```
mysql> show databases;
```

```
+--------------------+
| Database           |
+--------------------+
| information_schema |
| hive               |
| hue                |
| mysql              |
| oozie              |
| performance_schema |
| rman               |
| scm                |
| sentry             |
+--------------------+
9 rows in set (0.00 sec)
```

