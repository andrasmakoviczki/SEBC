# Result of ernest SHOW TABLES

```
0: jdbc:hive2://node1:10000/default> SHOW TABLES;
```

```
INFO  : Compiling command(queryId=hive_20171020100101_8c6746ee-e6b4-4801-9bd1-c3f0ad8c3658): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171020100101_8c6746ee-e6b4-4801-9bd1-c3f0ad8c3658); Time taken: 0.204 seconds
INFO  : Executing command(queryId=hive_20171020100101_8c6746ee-e6b4-4801-9bd1-c3f0ad8c3658): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171020100101_8c6746ee-e6b4-4801-9bd1-c3f0ad8c3658); Time taken: 0.24 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.591 seconds)
```

# Result of siwicki SHOW TABLES

```
0: jdbc:hive2://node1:10000/default> SHOW TABLES;
```

```
INFO  : Compiling command(queryId=hive_20171020100101_6003e56a-fd8e-4e3f-ace3-21b9488a551b): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171020100101_6003e56a-fd8e-4e3f-ace3-21b9488a551b); Time taken: 0.157 seconds
INFO  : Executing command(queryId=hive_20171020100101_6003e56a-fd8e-4e3f-ace3-21b9488a551b): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171020100101_6003e56a-fd8e-4e3f-ace3-21b9488a551b); Time taken: 0.136 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| sample_07  |
| sample_08  |
+------------+--+
2 rows selected (0.427 seconds)
```