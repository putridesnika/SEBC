## Database Information

```
[centos@ip-172-31-29-133 ~]$ hostnamectl
   Static hostname: ip-172-31-29-133.ap-southeast-1.compute.internal
         Icon name: computer-vm
           Chassis: vm
        Machine ID: 05cb8c7b39fe0f70e3ce97e5beab809d
           Boot ID: 772581eceae848b6b1380c44af5b6b0e
    Virtualization: xen
  Operating System: CentOS Linux 7 (Core)
       CPE OS Name: cpe:/o:centos:centos:7
            Kernel: Linux 3.10.0-957.1.3.el7.x86_64
      Architecture: x86-64
	  
[centos@ip-172-31-29-133 yum.repos.d]$ hostname -f
ip-172-31-29-133.ap-southeast-1.compute.internal
[centos@ip-172-31-29-133 lib]$ sudo systemctl stop mariadb
[centos@ip-172-31-29-133 lib]$ sudo systemctl status mariadb
● mariadb.service - MariaDB database server
   Loaded: loaded (/usr/lib/systemd/system/mariadb.service; disabled; vendor preset: disabled)
   Active: inactive (dead)
   
[centos@ip-172-31-29-133 ~]$ sudo mysql -u root -p -e "status;"
Enter password:
--------------
mysql  Ver 15.1 Distrib 5.5.64-MariaDB, for Linux (x86_64) using readline 5.1

Connection id:          12
Current database:
Current user:           root@localhost
SSL:                    Not in use
Current pager:          stdout
Using outfile:          ''
Using delimiter:        ;
Server:                 MariaDB
Server version:         5.5.64-MariaDB MariaDB Server
Protocol version:       10
Connection:             Localhost via UNIX socket
Server characterset:    latin1
Db     characterset:    latin1
Client characterset:    utf8
Conn.  characterset:    utf8
UNIX socket:            /var/lib/mysql/mysql.sock
Uptime:                 58 min 13 sec

Threads: 1  Questions: 42  Slow queries: 0  Opens: 1  Flush tables: 2  Open tables: 27  Queries per second avg: 0.012
--------------

[centos@ip-172-31-29-133 ~]$
   

MariaDB [(none)]> SHOW DATABASES;
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
