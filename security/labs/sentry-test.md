# Sentry test

```
[andrasmakoviczki@ip-172-32-4-188 ~]$ kinit andrasmakoviczki
```

```
Password for andrasmakoviczki@COMPUTE.INTERNAL:
```

```
[andrasmakoviczki@ip-172-32-4-188 ~]$ beeline
```

```
Beeline version 1.1.0-cdh5.9.3 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-32-4-188.eu-central-1.compute.internal@COMPUTE.INTERNAL
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-32-4-188.eu-central-1.compute.internal@COMPUTE.INTERNAL
Connected to: Apache Hive (version 1.1.0-cdh5.9.3)
Driver: Hive JDBC (version 1.1.0-cdh5.9.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
1: jdbc:hive2://localhost:10000/default> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20171018204848_9f71add7-f4d7-4fca-9c66-718276cfc6c6): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171018204848_9f71add7-f4d7-4fca-9c66-718276cfc6c6); Time taken: 0.711 seconds
INFO  : Executing command(queryId=hive_20171018204848_9f71add7-f4d7-4fca-9c66-718276cfc6c6): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171018204848_9f71add7-f4d7-4fca-9c66-718276cfc6c6); Time taken: 0.267 seconds
INFO  : OK
+-----------+--+
| tab_name  |
+-----------+--+
+-----------+--+
No rows selected (2.318 seconds)
```

# Grant role

```
1: jdbc:hive2://localhost:10000/default> CREATE ROLE sentry_admin;
INFO  : Compiling command(queryId=hive_20171018205252_7aa7d52b-fb99-43b4-a4e9-ad9ecc72f29f): CREATE ROLE sentry_admin
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171018205252_7aa7d52b-fb99-43b4-a4e9-ad9ecc72f29f); Time taken: 0.099 seconds
INFO  : Executing command(queryId=hive_20171018205252_7aa7d52b-fb99-43b4-a4e9-ad9ecc72f29f): CREATE ROLE sentry_admin
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171018205252_7aa7d52b-fb99-43b4-a4e9-ad9ecc72f29f); Time taken: 0.784 seconds
INFO  : OK
No rows affected (0.898 seconds)
1: jdbc:hive2://localhost:10000/default> GRANT ALL ON SERVER server1 TO ROLE sentry_admin;
INFO  : Compiling command(queryId=hive_20171018205353_a8a49aa1-87f5-4277-ae7c-401e54222cd2): GRANT ALL ON SERVER server1 TO ROLE sentry_admin
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171018205353_a8a49aa1-87f5-4277-ae7c-401e54222cd2); Time taken: 0.134 seconds
INFO  : Executing command(queryId=hive_20171018205353_a8a49aa1-87f5-4277-ae7c-401e54222cd2): GRANT ALL ON SERVER server1 TO ROLE sentry_admin
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171018205353_a8a49aa1-87f5-4277-ae7c-401e54222cd2); Time taken: 0.087 seconds
INFO  : OK
No rows affected (0.237 seconds)
1: jdbc:hive2://localhost:10000/default> GRANT ROLE sentry_admin TO GROUP sebc;
INFO  : Compiling command(queryId=hive_20171018205454_cfc8cb9b-1697-440c-a619-158b222a17b2): GRANT ROLE sentry_admin TO GROUP sebc
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171018205454_cfc8cb9b-1697-440c-a619-158b222a17b2); Time taken: 0.068 seconds
INFO  : Executing command(queryId=hive_20171018205454_cfc8cb9b-1697-440c-a619-158b222a17b2): GRANT ROLE sentry_admin TO GROUP sebc
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171018205454_cfc8cb9b-1697-440c-a619-158b222a17b2); Time taken: 0.069 seconds
INFO  : OK
No rows affected (0.149 seconds)
1: jdbc:hive2://localhost:10000/default> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20171018205454_69a75ead-2156-4022-9488-b9a8ac430500): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171018205454_69a75ead-2156-4022-9488-b9a8ac430500); Time taken: 0.062 seconds
INFO  : Executing command(queryId=hive_20171018205454_69a75ead-2156-4022-9488-b9a8ac430500): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171018205454_69a75ead-2156-4022-9488-b9a8ac430500); Time taken: 0.124 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.251 seconds)
```

# Add new users

```
COMMAND="sudo groupadd selector"; \
HOSTS="node0 node1 node2 node3 node4"; \
for i in $HOSTS; do ssh -i BigDataSEBCkey.pem centos@$i $COMMAND; done

COMMAND="sudo groupadd inserters"; \
HOSTS="node0 node1 node2 node3 node4"; \
for i in $HOSTS; do ssh -i BigDataSEBCkey.pem centos@$i $COMMAND; done

COMMAND="sudo useradd -u 1100 -g selector george"; \
HOSTS="node0 node1 node2 node3 node4"; \
for i in $HOSTS; do ssh -i BigDataSEBCkey.pem centos@$i $COMMAND; done

COMMAND="sudo useradd -u 1200 -g inserters ferdinand"; \
HOSTS="node0 node1 node2 node3 node4"; \
for i in $HOSTS; do ssh -i BigDataSEBCkey.pem centos@$i $COMMAND; done
```

# Create new roles

```
1: jdbc:hive2://localhost:10000/default> CREATE ROLE reads;
INFO  : Compiling command(queryId=hive_20171018210101_95fd1748-4ff6-4b68-9191-f747ceae41ee): CREATE ROLE reads
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171018210101_95fd1748-4ff6-4b68-9191-f747ceae41ee); Time taken: 0.068 seconds
INFO  : Executing command(queryId=hive_20171018210101_95fd1748-4ff6-4b68-9191-f747ceae41ee): CREATE ROLE reads
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171018210101_95fd1748-4ff6-4b68-9191-f747ceae41ee); Time taken: 0.044 seconds
INFO  : OK
No rows affected (0.125 seconds)

1: jdbc:hive2://localhost:10000/default> CREATE ROLE writes;
INFO  : Compiling command(queryId=hive_20171018211818_f1c24a3a-5436-4bfe-931d-3ebb0599e4b1): CREATE ROLE writes
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171018211818_f1c24a3a-5436-4bfe-931d-3ebb0599e4b1); Time taken: 0.06 seconds
INFO  : Executing command(queryId=hive_20171018211818_f1c24a3a-5436-4bfe-931d-3ebb0599e4b1): CREATE ROLE writes
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171018211818_f1c24a3a-5436-4bfe-931d-3ebb0599e4b1); Time taken: 0.027 seconds
INFO  : OK
No rows affected (0.103 seconds)
```

# Grant read privilege to reads

```
1: jdbc:hive2://localhost:10000/default> GRANT SELECT ON DATABASE default TO ROLE reads;
INFO  : Compiling command(queryId=hive_20171018210303_ab20cefd-79eb-4cd5-aec1-7b1e68313be9): GRANT SELECT ON DATABASE default TO ROLE reads
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171018210303_ab20cefd-79eb-4cd5-aec1-7b1e68313be9); Time taken: 0.056 seconds
INFO  : Executing command(queryId=hive_20171018210303_ab20cefd-79eb-4cd5-aec1-7b1e68313be9): GRANT SELECT ON DATABASE default TO ROLE reads
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171018210303_ab20cefd-79eb-4cd5-aec1-7b1e68313be9); Time taken: 0.04 seconds
INFO  : OK
No rows affected (0.108 seconds)

1: jdbc:hive2://localhost:10000/default> GRANT ROLE reads TO GROUP selector;
INFO  : Compiling command(queryId=hive_20171018210303_dfad957e-29c1-45cd-b64b-63975e8dde0c): GRANT ROLE reads TO GROUP selector
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171018210303_dfad957e-29c1-45cd-b64b-63975e8dde0c); Time taken: 0.055 seconds
INFO  : Executing command(queryId=hive_20171018210303_dfad957e-29c1-45cd-b64b-63975e8dde0c): GRANT ROLE reads TO GROUP selector
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171018210303_dfad957e-29c1-45cd-b64b-63975e8dde0c); Time taken: 0.028 seconds
INFO  : OK
No rows affected (0.098 seconds)
```

# Grant read privilege to writes

```
0: jdbc:hive2://localhost:10000/default> REVOKE ALL ON DATABASE default FROM ROLE writes;
INFO  : Compiling command(queryId=hive_20171018211818_3e6e6b44-dd91-4c86-90ea-d02e8a75f8a7): REVOKE ALL ON DATABASE default FROM ROLE writes
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171018211818_3e6e6b44-dd91-4c86-90ea-d02e8a75f8a7); Time taken: 0.065 seconds
INFO  : Executing command(queryId=hive_20171018211818_3e6e6b44-dd91-4c86-90ea-d02e8a75f8a7): REVOKE ALL ON DATABASE default FROM ROLE writes
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171018211818_3e6e6b44-dd91-4c86-90ea-d02e8a75f8a7); Time taken: 0.054 seconds
INFO  : OK
No rows affected (0.131 seconds)

0: jdbc:hive2://localhost:10000/default> GRANT SELECT ON default.sample_07 TO ROLE writes;
INFO  : Compiling command(queryId=hive_20171018211818_825903b4-4f1e-441f-8d8a-f2882e6eeaf0): GRANT SELECT ON default.sample_07 TO ROLE writes
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171018211818_825903b4-4f1e-441f-8d8a-f2882e6eeaf0); Time taken: 0.079 seconds
INFO  : Executing command(queryId=hive_20171018211818_825903b4-4f1e-441f-8d8a-f2882e6eeaf0): GRANT SELECT ON default.sample_07 TO ROLE writes
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171018211818_825903b4-4f1e-441f-8d8a-f2882e6eeaf0); Time taken: 0.029 seconds
INFO  : OK
No rows affected (0.121 seconds)

0: jdbc:hive2://localhost:10000/default> GRANT ROLE writes TO GROUP inserters;
INFO  : Compiling command(queryId=hive_20171018211818_406a1de6-091b-4fab-a058-e7f8e5c05fa3): GRANT ROLE writes TO GROUP inserters
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171018211818_406a1de6-091b-4fab-a058-e7f8e5c05fa3); Time taken: 0.062 seconds
INFO  : Executing command(queryId=hive_20171018211818_406a1de6-091b-4fab-a058-e7f8e5c05fa3): GRANT ROLE writes TO GROUP inserters
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171018211818_406a1de6-091b-4fab-a058-e7f8e5c05fa3); Time taken: 0.047 seconds
INFO  : OK
No rows affected (0.121 seconds)
```

# Show tables per users

## George

```
[centos@ip-172-32-4-188 ~]$ kinit george
```

```
Password for george@COMPUTE.INTERNAL:
```

```
[centos@ip-172-32-4-188 ~]$ beeline

```
Beeline version 1.1.0-cdh5.9.3 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-32-4-188.eu-central-1.compute.internal@COMPUTE.INTERNAL
scan complete in 3ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-32-4-188.eu-central-1.compute.internal@COMPUTE.INTERNAL
Connected to: Apache Hive (version 1.1.0-cdh5.9.3)
Driver: Hive JDBC (version 1.1.0-cdh5.9.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20171018212020_9702c55f-2cf5-48a1-8877-9badd8c8bf18): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171018212020_9702c55f-2cf5-48a1-8877-9badd8c8bf18); Time taken: 0.211 seconds
INFO  : Executing command(queryId=hive_20171018212020_9702c55f-2cf5-48a1-8877-9badd8c8bf18): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171018212020_9702c55f-2cf5-48a1-8877-9badd8c8bf18); Time taken: 0.195 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.568 seconds)
```

## Ferdinand

```
[centos@ip-172-32-4-188 ~]$ kinit ferdinand
Password for ferdinand@COMPUTE.INTERNAL:
[centos@ip-172-32-4-188 ~]$ beeline
Beeline version 1.1.0-cdh5.9.3 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-32-4-188.eu-central-1.compute.internal@COMPUTE.INTERNAL
scan complete in 2ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-32-4-188.eu-central-1.compute.internal@COMPUTE.INTERNAL
Connected to: Apache Hive (version 1.1.0-cdh5.9.3)
Driver: Hive JDBC (version 1.1.0-cdh5.9.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20171018212222_081e1997-e6e9-47ba-a8a1-2a95549a651b): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171018212222_081e1997-e6e9-47ba-a8a1-2a95549a651b); Time taken: 0.091 seconds
INFO  : Executing command(queryId=hive_20171018212222_081e1997-e6e9-47ba-a8a1-2a95549a651b): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171018212222_081e1997-e6e9-47ba-a8a1-2a95549a651b); Time taken: 0.133 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| sample_07  |
+------------+--+
1 row selected (0.314 seconds)
```