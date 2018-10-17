```
[grcancelliere@grcsebcm ~]$ beeline
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Beeline version 1.1.0-cdh5.13.3 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/grcsebcm@HADOOP.COM
scan complete in 3ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/grcsebcm@HADOOP.COM
Connected to: Apache Hive (version 1.1.0-cdh5.13.3)
Driver: Hive JDBC (version 1.1.0-cdh5.13.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20181017175555_85201066-f35d-4fc5-8f15-c09b104b584a): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20181017175555_85201066-f35d-4fc5-8f15-c09b104b584a); Time taken: 0.724 seconds
INFO  : Executing command(queryId=hive_20181017175555_85201066-f35d-4fc5-8f15-c09b104b584a): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20181017175555_85201066-f35d-4fc5-8f15-c09b104b584a); Time taken: 0.427 seconds
INFO  : OK
+-----------+--+
| tab_name  |
+-----------+--+
+-----------+--+
No rows selected (2.549 seconds)
```
```
[grcancelliere@grcsebcm ~]$ kinit
Password for grcancelliere@HADOOP.COM:
[grcancelliere@grcsebcm ~]$ beeline
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Beeline version 1.1.0-cdh5.13.3 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/grcsebcm@HADOOP.COM
scan complete in 2ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/grcsebcm@HADOOP.COM
Connected to: Apache Hive (version 1.1.0-cdh5.13.3)
Driver: Hive JDBC (version 1.1.0-cdh5.13.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20181017182727_e0812375-1489-4d92-9e68-b0beaf0abd0a): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20181017182727_e0812375-1489-4d92-9e68-b0beaf0abd0a); Time taken: 0.078 seconds
INFO  : Executing command(queryId=hive_20181017182727_e0812375-1489-4d92-9e68-b0beaf0abd0a): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20181017182727_e0812375-1489-4d92-9e68-b0beaf0abd0a); Time taken: 0.222 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.405 seconds)
```
```
[grcancelliere@grcsebcm ~]$ sudo groupadd selector
[grcancelliere@grcsebcm ~]$ sudo groupadd inserters
[grcancelliere@grcsebcm ~]$ sudo useradd -u 1100 -g selector george
[grcancelliere@grcsebcm ~]$ sudo useradd -u 1200 -g inserters ferdinand
[grcancelliere@grcsebcm ~]$ sudo su
[root@grcsebcm grcancelliere]# kadmin -q 'add_principal george'
Authenticating as principal admin/admin@HADOOP.COM with password.
Password for admin/admin@HADOOP.COM:
WARNING: no policy specified for george@HADOOP.COM; defaulting to no policy
Enter password for principal "george@HADOOP.COM":
Re-enter password for principal "george@HADOOP.COM":
Principal "george@HADOOP.COM" created.
[root@grcsebcm grcancelliere]# kadmin -q 'add_principal ferdinand'
Authenticating as principal admin/admin@HADOOP.COM with password.
Password for admin/admin@HADOOP.COM:
WARNING: no policy specified for ferdinand@HADOOP.COM; defaulting to no policy
Enter password for principal "ferdinand@HADOOP.COM":
Re-enter password for principal "ferdinand@HADOOP.COM":
Principal "ferdinand@HADOOP.COM" created.
```
```
0: jdbc:hive2://localhost:10000/default> create role reads;
INFO  : Compiling command(queryId=hive_20181017182828_488a7a51-9af9-4460-a47b-eabf8565769a): create role reads
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20181017182828_488a7a51-9af9-4460-a47b-eabf8565769a); Time taken: 0.081 seconds
INFO  : Executing command(queryId=hive_20181017182828_488a7a51-9af9-4460-a47b-eabf8565769a): create role reads
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20181017182828_488a7a51-9af9-4460-a47b-eabf8565769a); Time taken: 0.033 seconds
INFO  : OK
No rows affected (0.123 seconds)
0: jdbc:hive2://localhost:10000/default> create role writes;
INFO  : Compiling command(queryId=hive_20181017182828_4b327214-fe64-45b5-b757-1526a4984067): create role writes
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20181017182828_4b327214-fe64-45b5-b757-1526a4984067); Time taken: 0.057 seconds
INFO  : Executing command(queryId=hive_20181017182828_4b327214-fe64-45b5-b757-1526a4984067): create role writes
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20181017182828_4b327214-fe64-45b5-b757-1526a4984067); Time taken: 0.018 seconds
INFO  : OK
No rows affected (0.086 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT SELECT ON DATABASE default TO ROLE reads;
INFO  : Compiling command(queryId=hive_20181017182828_336dfb12-aa07-4f8a-8d87-85b1c7917791): GRANT SELECT ON DATABASE default TO ROLE reads
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20181017182828_336dfb12-aa07-4f8a-8d87-85b1c7917791); Time taken: 0.064 seconds
INFO  : Executing command(queryId=hive_20181017182828_336dfb12-aa07-4f8a-8d87-85b1c7917791): GRANT SELECT ON DATABASE default TO ROLE reads
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20181017182828_336dfb12-aa07-4f8a-8d87-85b1c7917791); Time taken: 0.02 seconds
INFO  : OK
No rows affected (0.094 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT ROLE reads TO GROUP selector;
INFO  : Compiling command(queryId=hive_20181017182828_564f6dda-35a4-4763-91e9-5f6216db21ed): GRANT ROLE reads TO GROUP selector
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20181017182828_564f6dda-35a4-4763-91e9-5f6216db21ed); Time taken: 0.056 seconds
INFO  : Executing command(queryId=hive_20181017182828_564f6dda-35a4-4763-91e9-5f6216db21ed): GRANT ROLE reads TO GROUP selector
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20181017182828_564f6dda-35a4-4763-91e9-5f6216db21ed); Time taken: 0.014 seconds
INFO  : OK
No rows affected (0.081 seconds)
```
```
0: jdbc:hive2://localhost:10000/default> REVOKE ALL ON DATABASE default FROM ROLE writes;
INFO  : Compiling command(queryId=hive_20181017183030_e7f0dab7-3273-40a3-9d91-76cd48410f0e): REVOKE ALL ON DATABASE default FROM ROLE writes
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20181017183030_e7f0dab7-3273-40a3-9d91-76cd48410f0e); Time taken: 0.056 seconds
INFO  : Executing command(queryId=hive_20181017183030_e7f0dab7-3273-40a3-9d91-76cd48410f0e): REVOKE ALL ON DATABASE default FROM ROLE writes
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20181017183030_e7f0dab7-3273-40a3-9d91-76cd48410f0e); Time taken: 0.05 seconds
INFO  : OK
No rows affected (0.115 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT SELECT ON default.sample_07 TO ROLE writes;
INFO  : Compiling command(queryId=hive_20181017183030_821f55c2-70f6-4ec4-8b11-ea58b1ddf71a): GRANT SELECT ON default.sample_07 TO ROLE writes
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20181017183030_821f55c2-70f6-4ec4-8b11-ea58b1ddf71a); Time taken: 0.059 seconds
INFO  : Executing command(queryId=hive_20181017183030_821f55c2-70f6-4ec4-8b11-ea58b1ddf71a): GRANT SELECT ON default.sample_07 TO ROLE writes
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20181017183030_821f55c2-70f6-4ec4-8b11-ea58b1ddf71a); Time taken: 0.02 seconds
INFO  : OK
No rows affected (0.087 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT ROLE writes TO GROUP inserters;
INFO  : Compiling command(queryId=hive_20181017183030_b8eab4c4-ff0f-4c36-85ab-76ad469b707b): GRANT ROLE writes TO GROUP inserters
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20181017183030_b8eab4c4-ff0f-4c36-85ab-76ad469b707b); Time taken: 0.056 seconds
INFO  : Executing command(queryId=hive_20181017183030_b8eab4c4-ff0f-4c36-85ab-76ad469b707b): GRANT ROLE writes TO GROUP inserters
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20181017183030_b8eab4c4-ff0f-4c36-85ab-76ad469b707b); Time taken: 0.015 seconds
INFO  : OK
No rows affected (0.085 seconds)
```
```
[grcancelliere@grcsebcm ~]$ kinit george@HADOOP.COM
Password for george@HADOOP.COM:
[grcancelliere@grcsebcm ~]$ beeline
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Beeline version 1.1.0-cdh5.13.3 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/grcsebcm@HADOOP.COM
scan complete in 2ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/grcsebcm@HADOOP.COM
Connected to: Apache Hive (version 1.1.0-cdh5.13.3)
Driver: Hive JDBC (version 1.1.0-cdh5.13.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20181017183434_6f297d9d-74f5-4bce-b250-61d443f9f4ec): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20181017183434_6f297d9d-74f5-4bce-b250-61d443f9f4ec); Time taken: 0.067 seconds
INFO  : Executing command(queryId=hive_20181017183434_6f297d9d-74f5-4bce-b250-61d443f9f4ec): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20181017183434_6f297d9d-74f5-4bce-b250-61d443f9f4ec); Time taken: 0.243 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.425 seconds)
```
```
[grcancelliere@grcsebcm ~]$ kinit ferdinand@HADOOP.COM
Password for ferdinand@HADOOP.COM:
[grcancelliere@grcsebcm ~]$ beeline
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Beeline version 1.1.0-cdh5.13.3 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/grcsebcm@HADOOP.COM
scan complete in 2ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/grcsebcm@HADOOP.COM
Connected to: Apache Hive (version 1.1.0-cdh5.13.3)
Driver: Hive JDBC (version 1.1.0-cdh5.13.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20181017183535_056aa1b5-a268-4edd-9368-b55afa401961): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20181017183535_056aa1b5-a268-4edd-9368-b55afa401961); Time taken: 0.072 seconds
INFO  : Executing command(queryId=hive_20181017183535_056aa1b5-a268-4edd-9368-b55afa401961): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20181017183535_056aa1b5-a268-4edd-9368-b55afa401961); Time taken: 0.213 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| sample_07  |
+------------+--+
1 row selected (0.405 seconds)
```