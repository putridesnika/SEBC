## Database Information

```

First Line Log
[centos@ip-172-31-17-158 ~]$ sudo tail -f /var/log/cloudera-scm-server/cloudera-scm-server.log
2020-01-10 13:14:52,666 INFO SearchRepositoryManager-0:com.cloudera.server.web.cmf.search.components.SearchRepositoryManager: Num docs:234

Startv Jetty Server 
2020-01-10 13:14:53,965 INFO WebServerImpl:org.eclipse.jetty.server.Server: Started @80108ms
2020-01-10 13:14:53,965 INFO WebServerImpl:com.cloudera.server.cmf.WebServerImpl: Started Jetty server.


DB Prpperties
# Auto-generated by scm_prepare_database.sh on Fri Jan 10 13:10:24 UTC 2020
#
# For information describing how to configure the Cloudera Manager Server
# to connect to databases, see the "Cloudera Manager Installation Guide."
#
com.cloudera.cmf.db.type=mysql
com.cloudera.cmf.db.host=172.31.29.133
com.cloudera.cmf.db.name=scm
com.cloudera.cmf.db.user=scm
com.cloudera.cmf.db.setupType=EXTERNAL
com.cloudera.cmf.db.password=welcome1
db.properties (END)






```