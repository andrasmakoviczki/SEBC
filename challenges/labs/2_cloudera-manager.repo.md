# Content of CM repo

```
[root@ip-172-32-9-75 ~]# cat /etc/yum.repos.d/cloudera-manager.repo
```

```
[cloudera-manager]
# Packages for Cloudera Manager, Version 5, on RedHat or CentOS 6 x86_64
name=Cloudera Manager
baseurl=https://archive.cloudera.com/cm5/redhat/6/x86_64/cm/5.9/
gpgkey =https://archive.cloudera.com/cm5/redhat/6/x86_64/cm/RPM-GPG-KEY-cloudera
gpgcheck = 1
```

# SCM prepare

```
[root@ip-172-32-7-232 ~]# /usr/share/cmf/schema/scm_prepare_database.sh mysql scm scm -p -h 172.32.9.75 -P 3306
```

```
Enter database password:
Enter SCM password:
JAVA_HOME=/usr/java/jre1.8.0_131
Verifying that we can write to /etc/cloudera-scm-server
Creating SCM configuration file in /etc/cloudera-scm-server
Executing:  /usr/java/jre1.8.0_131/bin/java -cp /usr/share/java/mysql-connector-java.jar:/usr/share/java/oracle-connector-java.jar:/usr/share/cmf/schema/../lib/* com.cloudera.enterprise.dbutil.DbCommandExecutor /etc/cloudera-scm-server/db.properties com.cloudera.cmf.db.
[                          main] DbCommandExecutor              INFO  Successfully connected to database.
All done, your SCM database is configured correctly!
```

