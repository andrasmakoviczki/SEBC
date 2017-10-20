# List of HDFS users

```
[root@ip-172-32-7-232 ~]# hdfs dfs -ls /user
```

```
Found 8 items
drwxr-xr-x   - andrasmakoviczki andrasmakoviczki          0 2017-10-20 08:52 /user/andrasmakoviczki
drwxr-xr-x   - ernest           usa                       0 2017-10-20 08:54 /user/ernest
drwxr-xr-x   - hdfs             supergroup                0 2017-10-20 08:51 /user/hdfs
drwxrwxrwx   - mapred           hadoop                    0 2017-10-20 08:45 /user/history
drwxrwxr-t   - hive             hive                      0 2017-10-20 08:46 /user/hive
drwxrwxr-x   - hue              hue                       0 2017-10-20 08:46 /user/hue
drwxrwxr-x   - oozie            oozie                     0 2017-10-20 08:47 /user/oozie
drwxr-xr-x   - siwicki          emea                      0 2017-10-20 08:48 /user/siwicki
```

# REST call (hosts)

```
[root@ip-172-32-7-232 ~]# curl -X GET -u "admin:admin" http://$(hostname -i):7180/api/v14/hosts
```

```
{
  "items" : [ {
    "hostId" : "i-0b5c8e7a42049cfa0",
    "ipAddress" : "172.32.10.103",
    "hostname" : "ip-172-32-10-103.eu-central-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-32-7-232.eu-central-1.compute.internal:7180/cmf/hostRedirect/i-0b5c8e7a42049cfa0",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15664549888
  }, {
    "hostId" : "i-09e252076c879aeea",
    "ipAddress" : "172.32.5.224",
    "hostname" : "ip-172-32-5-224.eu-central-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-32-7-232.eu-central-1.compute.internal:7180/cmf/hostRedirect/i-09e252076c879aeea",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15664549888
  }, {
    "hostId" : "i-0cbac5bab992ce6b0",
    "ipAddress" : "172.32.6.77",
    "hostname" : "ip-172-32-6-77.eu-central-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-32-7-232.eu-central-1.compute.internal:7180/cmf/hostRedirect/i-0cbac5bab992ce6b0",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15664549888
  }, {
    "hostId" : "i-0828898db4dce354f",
    "ipAddress" : "172.32.7.232",
    "hostname" : "ip-172-32-7-232.eu-central-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-32-7-232.eu-central-1.compute.internal:7180/cmf/hostRedirect/i-0828898db4dce354f",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15664549888
  }, {
    "hostId" : "i-057a141b80fd34815",
    "ipAddress" : "172.32.9.75",
    "hostname" : "ip-172-32-9-75.eu-central-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-32-7-232.eu-central-1.compute.internal:7180/cmf/hostRedirect/i-057a141b80fd34815",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15664549888
  } ]
}
```
