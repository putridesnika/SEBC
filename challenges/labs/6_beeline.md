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

```
1,000 rows selected (1.638 seconds)
0: jdbc:hive2://localhost:10000/default> select * from web_logs limit 10;
INFO  : Compiling command(queryId=hive_20180517085656_5b98e433-001a-4f63-abdd-a9000dd5f92a): select * from web_logs limit 10
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:web_logs._version_, type:bigint, comment:null), FieldSchema(name:web_logs.app, type:string, comment:null), FieldSchema(name:web_logs.bytes, type:smallint, comment:null), FieldSchema(name:web_logs.city, type:string, comment:null), FieldSchema(name:web_logs.client_ip, type:string, comment:null), FieldSchema(name:web_logs.code, type:tinyint, comment:null), FieldSchema(name:web_logs.country_code, type:string, comment:null), FieldSchema(name:web_logs.country_code3, type:string, comment:null), FieldSchema(name:web_logs.country_name, type:string, comment:null), FieldSchema(name:web_logs.device_family, type:string, comment:null), FieldSchema(name:web_logs.extension, type:string, comment:null), FieldSchema(name:web_logs.latitude, type:float, comment:null), FieldSchema(name:web_logs.longitude, type:float, comment:null), FieldSchema(name:web_logs.method, type:string, comment:null), FieldSchema(name:web_logs.os_family, type:string, comment:null), FieldSchema(name:web_logs.os_major, type:string, comment:null), FieldSchema(name:web_logs.protocol, type:string, comment:null), FieldSchema(name:web_logs.record, type:string, comment:null), FieldSchema(name:web_logs.referer, type:string, comment:null), FieldSchema(name:web_logs.region_code, type:bigint, comment:null), FieldSchema(name:web_logs.request, type:string, comment:null), FieldSchema(name:web_logs.subapp, type:string, comment:null), FieldSchema(name:web_logs.time, type:string, comment:null), FieldSchema(name:web_logs.url, type:string, comment:null), FieldSchema(name:web_logs.user_agent, type:string, comment:null), FieldSchema(name:web_logs.user_agent_family, type:string, comment:null), FieldSchema(name:web_logs.user_agent_major, type:string, comment:null), FieldSchema(name:web_logs.id, type:string, comment:null), FieldSchema(name:web_logs.date, type:string, comment:null)], properties:null)
INFO  : Completed compiling command(queryId=hive_20180517085656_5b98e433-001a-4f63-abdd-a9000dd5f92a); Time taken: 0.164 seconds
INFO  : Executing command(queryId=hive_20180517085656_5b98e433-001a-4f63-abdd-a9000dd5f92a): select * from web_logs limit 10
INFO  : Completed executing command(queryId=hive_20180517085656_5b98e433-001a-4f63-abdd-a9000dd5f92a); Time taken: 0.002 seconds
INFO  : OK
+----------------------+---------------+-----------------+----------------+---------------------+----------------+------------------------+-------------------------+------------------------+-------------------------+---------------------+---------------------+----------------------+------------------+---------------------+--------------------+--------------------+------------------+----------------------------------------------------+-----------------------+----------------------------------------------------+------------------+-----------------------+----------------------------------------------------+----------------------------------------------------+----------------------------------------------------+----------------------------+---------------------------------------+----------------+--+
|  web_logs._version_  | web_logs.app  | web_logs.bytes  | web_logs.city  | web_logs.client_ip  | web_logs.code  | web_logs.country_code  | web_logs.country_code3  | web_logs.country_name  | web_logs.device_family  | web_logs.extension  |  web_logs.latitude  |  web_logs.longitude  | web_logs.method  | web_logs.os_family  | web_logs.os_major  | web_logs.protocol  | web_logs.record  |                  web_logs.referer                  | web_logs.region_code  |                  web_logs.request                  | web_logs.subapp  |     web_logs.time     |                    web_logs.url                    |                web_logs.user_agent                 |             web_logs.user_agent_family             | web_logs.user_agent_major  |              web_logs.id              | web_logs.date  |
+----------------------+---------------+-----------------+----------------+---------------------+----------------+------------------------+-------------------------+------------------------+-------------------------+---------------------+---------------------+----------------------+------------------+---------------------+--------------------+--------------------+------------------+----------------------------------------------------+-----------------------+----------------------------------------------------+------------------+-----------------------+----------------------------------------------------+----------------------------------------------------+----------------------------------------------------+----------------------------+---------------------------------------+----------------+--+
| 1480895575515725824  | metastore     | 1041            | Singapore      | 128.199.234.236     | NULL           | SG                     | SGP                     | Singapore              | Other                   |                     | 1.2930999994277954  | 103.85579681396484   | GET              | Other               |                    | HTTP/1.1           |                  | -                                                  | 0                     | GET /metastore/table/default/sample_07 HTTP/1.1    | table            | 2014-05-04T06:35:49Z  | /metastore/table/default/sample_07                 | Mozilla/5.0 (compatible; phpservermon/3.0.1; +http://www.phpservermonitor.org) | Other                                              |                            | 8836e6ce-9a21-449f-a372-9e57641389b3  | 2015-11-18     |
| 1480895575528308736  | metastore     | 1041            | Singapore      | 128.199.234.236     | NULL           | SG                     | SGP                     | Singapore              | Other                   |                     | 1.2930999994277954  | 103.85579681396484   | GET              | Other               |                    | HTTP/1.1           |                  | -                                                  | 0                     | GET /metastore/table/default/sample_07 HTTP/1.1    | table            | 2014-05-04T06:35:50Z  | /metastore/table/default/sample_07                 | Mozilla/5.0 (compatible; phpservermon/3.0.1; +http://www.phpservermonitor.org) | Other                                              |                            | 6ddf6e38-7b83-423c-8873-39842dca2dbb  | 2015-11-18     |
| 1480895575528308737  | search        | 1041            | Singapore      | 128.199.234.236     | NULL           | SG                     | SGP                     | Singapore              | Other                   |                     | 1.2930999994277954  | 103.85579681396484   | GET              | Other               |                    | HTTP/1.1           |                  | -                                                  | 0                     | GET /search/?collection=10000001 HTTP/1.1          |                  | 2014-05-04T06:35:52Z  | /search/?collection=10000001                       | Mozilla/5.0 (compatible; phpservermon/3.0.1; +http://www.phpservermonitor.org) | Other                                              |                            | 313bb28e-dd7c-4364-a11e-9ffb0db7b303  | 2015-11-18     |
| 1480895575528308738  | search        | 1041            | Singapore      | 128.199.234.236     | NULL           | SG                     | SGP                     | Singapore              | Other                   |                     | 1.2930999994277954  | 103.85579681396484   | GET              | Other               |                    | HTTP/1.1           |                  | -                                                  | 0                     | GET /search/?collection=10000001 HTTP/1.1          |                  | 2014-05-04T06:35:53Z  | /search/?collection=10000001                       | Mozilla/5.0 (compatible; phpservermon/3.0.1; +http://www.phpservermonitor.org) | Other                                              |                            | ecb47c61-a9e4-4b59-9234-04bd57695987  | 2015-11-18     |
| 1480895575528308739  |               | 238             | Singapore      | 128.199.234.236     | NULL           | SG                     | SGP                     | Singapore              | Other                   |                     | 1.2930999994277954  | 103.85579681396484   | HEAD             | Other               |                    | HTTP/1.1           |                  | -                                                  | 0                     | HEAD / HTTP/1.1                                    |                  | 2014-05-04T06:35:54Z  | /                                                  | Mozilla/5.0 (compatible; phpservermon/3.0.1; +http://www.phpservermonitor.org) | Other                                              |                            | affdb6b9-3657-4d15-8af8-2ba2f3a69343  | 2015-11-18     |
| 1480895575528308740  | beeswax       | 1041            | Mountain View  | 66.249.76.236       | NULL           | US                     | USA                     | United States          | Spider                  |                     | 37.38600158691406   | -122.08380126953125  | GET              | Other               |                    | HTTP/1.1           |                  | -                                                  | NULL                  | GET /beeswax/query_history?q-type=beeswax&amp;q-user=dy8515s&amp;q-auto_query=off HTTP/1.1 |                  | 2014-05-04T06:35:54Z  | /beeswax/query_history?q-type=beeswax&amp;q-user=dy8515s&amp;q-auto_query=off | Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html) | Googlebot                                          | 2                          | e3f88d9e-7e5b-4ef7-8941-c0d83720616c  | 2015-11-18     |
| 1480895575528308741  |               | 1041            | Guiyang        | 222.85.131.87       | NULL           | CN                     | CHN                     | China                  | Other                   |                     | 26.58329963684082   | 106.7166976928711    | GET              | Windows 7           |                    | HTTP/1.1           |                  | -                                                  | 18                    | GET / HTTP/1.1                                     |                  | 2014-05-04T06:35:55Z  | /                                                  | Mozilla/5.0 (compatible; MSIE 10.0; Windows NT 6.1; Trident/6.0) | IE                                                 | 10                         | 4dbb1f74-6856-4fe3-8515-c53eab600b60  | 2015-11-18     |
| 1480895575529357312  | desktop       | 0               | Guiyang        | 222.85.131.87       | NULL           | CN                     | CHN                     | China                  | Other                   |                     | 26.58329963684082   | 106.7166976928711    |                  | Other               |                    |                    |                  | -                                                  | 18                    | -                                                  |                  | 2014-05-04T06:36:16Z  |                                                    | -                                                  | Other                                              |                            | 86cdb56d-99c0-4701-a842-472741bb833a  | 2015-11-18     |
| 1480895575529357313  | search        | 1041            | Shanghai       | 101.226.168.225     | NULL           | CN                     | CHN                     | China                  | Other                   |                     | 31.04560089111328   | 121.39969635009766   | GET              | Windows 7           |                    | HTTP/1.1           |                  | http://demo.gethue.com/search/?collection=10000001&amp;fq=%7Cuser_statuses_count%3A%5B%229000%22%20TO%20%229999%22%5D%7Cuser_location%3A%22new%20york%22&amp;query&amp;rows=15&amp;start=0 | 23                    | GET /search/?collection=10000001&amp;fq=%7Cuser_statuses_count%3A%5B%229000%22%20TO%20%229999%22%5D%7Cuser_location%3A%22new%20york%22&amp;query&amp;rows=15&amp;start=0 HTTP/1.1 |                  | 2014-05-04T06:38:31Z  | /search/?collection=10000001&amp;fq=%7Cuser_statuses_count%3A%5B%229000%22%20TO%20%229999%22%5D%7Cuser_location%3A%22new%20york%22&amp;query&amp;rows=15&amp;start=0 | "Mozilla/5.0 (Windows NT 6.1) AppleWebKit/537.1 (KHTML |  like Gecko) Chrome/21.0.1180.89 Safari/537.1; 360Spider" | Chrome                     | 21                                    | 2015-11-18     |
| 1480895575529357314  | search        | 1041            | Mountain View  | 66.249.76.225       | NULL           | US                     | USA                     | United States          | Spider                  |                     | 37.38600158691406   | -122.08380126953125  | GET              | Other               |                    | HTTP/1.1           |                  | -                                                  | NULL                  | GET /search/?collection=10000001&amp;query=&amp;fq=%7Cuser_followers_count%3A%5B%22100%22%20TO%20%22199%22%5D%7Cuser_location%3A%22philippines%22&amp;rows=15&amp;start=240 HTTP/1.1 |                  | 2014-05-04T06:38:55Z  | /search/?collection=10000001&amp;query=&amp;fq=%7Cuser_followers_count%3A%5B%22100%22%20TO%20%22199%22%5D%7Cuser_location%3A%22philippines%22&amp;rows=15&amp;start=240 | Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html) | Googlebot                                          | 2                          | 8260ca42-55d6-4cd4-8beb-8767826dc929  | 2015-11-18     |
+----------------------+---------------+-----------------+----------------+---------------------+----------------+------------------------+-------------------------+------------------------+-------------------------+---------------------+---------------------+----------------------+------------------+---------------------+--------------------+--------------------+------------------+----------------------------------------------------+-----------------------+----------------------------------------------------+------------------+-----------------------+----------------------------------------------------+----------------------------------------------------+----------------------------------------------------+----------------------------+---------------------------------------+----------------+--+
10 rows selected (0.255 seconds)
0: jdbc:hive2://localhost:10000/default> exit
. . . . . . . . . . . . . . . . . . . .> [root@ip-172-30-1-171 188-hive-HIVESERVER2]# kinit bertran
kinit: Client 'bertran@DODDYS.SG' not found in Kerberos database while getting initial credentials
[root@ip-172-30-1-171 188-hive-HIVESERVER2]# kinit beltran
Password for beltran@DODDYS.SG:
[root@ip-172-30-1-171 188-hive-HIVESERVER2]# beeline
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Java HotSpot(TM) 64-Bit Server VM warning: Using incremental CMS is deprecated and will likely be removed in a future release
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Beeline version 1.1.0-cdh5.13.3 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-30-1-171.ap-southeast-1.compute.internal@DODDYS.SG
scan complete in 2ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-30-1-171.ap-southeast-1.compute.internal@DODDYS.SG
Connected to: Apache Hive (version 1.1.0-cdh5.13.3)
Driver: Hive JDBC (version 1.1.0-cdh5.13.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> select * from customers limit 10;
Error: Error while compiling statement: FAILED: SemanticException No valid privileges
 User beltran does not have privileges for QUERY
 The required privileges: Server=server1->Db=default->Table=customers->Column=addresses->action=select; (state=42000,code=40000)

 ```
 
