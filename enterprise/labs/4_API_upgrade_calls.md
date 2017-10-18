# Latest Api version

```
[root@ip-172-32-9-69 ~]# curl -u andrasmakoviczki:cloudera http://35.158.41.226:7180/api/version
```

```
v14
```

# CM version

```
[root@ip-172-32-9-69 ~]# curl -u andrasmakoviczki:cloudera http://35.158.41.226:7180/api/v14/cm/version
```

```
{
  "version" : "5.9.3",
  "buildUser" : "jenkins",
  "buildTimestamp" : "20170627-1506",
  "gitHash" : "23506bb4e114dd460bdac64c57a672e6be631907",
  "snapshot" : false
}
```

# CM users

```
[root@ip-172-32-9-69 ~]# curl -u andrasmakoviczki:cloudera http://35.158.41.226:7180/api/v14/users
```

```
{
  "items" : [ {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ]
  }, {
    "name" : "andrasmakoviczki",
    "roles" : [ "ROLE_ADMIN" ]
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ]
  } ]
}
```

# Database info

```
[root@ip-172-32-9-69 ~]# curl -u andrasmakoviczki:cloudera http://35.158.41.226:7180/api/v14/cm/scmDbInfo
```

```
{
  "scmDbType" : "MYSQL",
  "embeddedDbUsed" : false
}
```