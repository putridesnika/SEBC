## Beeline

```
[root@ip-172-30-1-171 188-hive-HIVESERVER2]# kinit -kt hive.keytab hive/ip-172-30-1-171.ap-southeast-1.compute.internal@DODDYS.SG
[root@ip-172-30-1-171 188-hive-HIVESERVER2]# beeline
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Java HotSpot(TM) 64-Bit Server VM warning: Using incremental CMS is deprecated and will likely be removed in a future release
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Beeline version 1.1.0-cdh5.13.3 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-30-1-171.ap-southeast-1.compute.internal@DODDYS.SG
scan complete in 1ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-30-1-171.ap-southeast-1.compute.internal@DODDYS.SG
Connected to: Apache Hive (version 1.1.0-cdh5.13.3)
Driver: Hive JDBC (version 1.1.0-cdh5.13.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> CREATE ROLE HttpViewer;
INFO  : Compiling command(queryId=hive_20180517085050_89f06796-f8e7-4454-be53-9b0fdd38c809): CREATE ROLE HttpViewer
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20180517085050_89f06796-f8e7-4454-be53-9b0fdd38c809); Time taken: 0.588 seconds
INFO  : Executing command(queryId=hive_20180517085050_89f06796-f8e7-4454-be53-9b0fdd38c809): CREATE ROLE HttpViewer
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20180517085050_89f06796-f8e7-4454-be53-9b0fdd38c809); Time taken: 0.207 seconds
INFO  : OK
No rows affected (2.147 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT SELECT ON default.web_logs TO ROLE HttpViewer;
INFO  : Compiling command(queryId=hive_20180517085151_32dc23d7-432c-4a04-b38f-df965ecc4fde): GRANT SELECT ON default.web_logs TO ROLE HttpViewer
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20180517085151_32dc23d7-432c-4a04-b38f-df965ecc4fde); Time taken: 0.1 seconds
INFO  : Executing command(queryId=hive_20180517085151_32dc23d7-432c-4a04-b38f-df965ecc4fde): GRANT SELECT ON default.web_logs TO ROLE HttpViewer
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20180517085151_32dc23d7-432c-4a04-b38f-df965ecc4fde); Time taken: 0.074 seconds
INFO  : OK
No rows affected (0.186 seconds)
0: jdbc:hive2://localhost:10000/default>
0: jdbc:hive2://localhost:10000/default> GRANT ROLE HttpViewer TO GROUP rangers;
INFO  : Compiling command(queryId=hive_20180517085151_c226a5dc-84fc-444d-ab37-95c9b1681f8f): GRANT ROLE HttpViewer TO GROUP rangers
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20180517085151_c226a5dc-84fc-444d-ab37-95c9b1681f8f); Time taken: 0.07 seconds
INFO  : Executing command(queryId=hive_20180517085151_c226a5dc-84fc-444d-ab37-95c9b1681f8f): GRANT ROLE HttpViewer TO GROUP rangers
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20180517085151_c226a5dc-84fc-444d-ab37-95c9b1681f8f); Time taken: 0.046 seconds
INFO  : OK
No rows affected (0.131 seconds)
0: jdbc:hive2://localhost:10000/default> CREATE ROLE ServiceViewer;
INFO  : Compiling command(queryId=hive_20180517085151_63b07859-4a51-4f16-bc02-e12bec02fa9b): CREATE ROLE ServiceViewer
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20180517085151_63b07859-4a51-4f16-bc02-e12bec02fa9b); Time taken: 0.062 seconds
INFO  : Executing command(queryId=hive_20180517085151_63b07859-4a51-4f16-bc02-e12bec02fa9b): CREATE ROLE ServiceViewer
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20180517085151_63b07859-4a51-4f16-bc02-e12bec02fa9b); Time taken: 0.009 seconds
INFO  : OK
No rows affected (0.083 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT SELECT ON default.customer TO ROLE ServiceViewer;
INFO  : Compiling command(queryId=hive_20180517085151_135abf76-783f-4f8e-86e3-e50c157d9232): GRANT SELECT ON default.customer TO ROLE ServiceViewer
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20180517085151_135abf76-783f-4f8e-86e3-e50c157d9232); Time taken: 0.078 seconds
INFO  : Executing command(queryId=hive_20180517085151_135abf76-783f-4f8e-86e3-e50c157d9232): GRANT SELECT ON default.customer TO ROLE ServiceViewer
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20180517085151_135abf76-783f-4f8e-86e3-e50c157d9232); Time taken: 0.011 seconds
INFO  : OK
No rows affected (0.099 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT ROLE HttpViewer TO GROUP astros;
INFO  : Compiling command(queryId=hive_20180517085151_0d702e55-b49b-4999-9ca7-411b1a538f75): GRANT ROLE HttpViewer TO GROUP astros
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20180517085151_0d702e55-b49b-4999-9ca7-411b1a538f75); Time taken: 0.059 seconds
INFO  : Executing command(queryId=hive_20180517085151_0d702e55-b49b-4999-9ca7-411b1a538f75): GRANT ROLE HttpViewer TO GROUP astros
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20180517085151_0d702e55-b49b-4999-9ca7-411b1a538f75); Time taken: 0.009 seconds
INFO  : OK
No rows affected (0.085 seconds)
0: jdbc:hive2://localhost:10000/default>

```
