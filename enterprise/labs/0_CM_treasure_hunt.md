# What is ubertask optimization?

This is a job related option. It can runs "sufficiently small" jobs sequentially within a single JVM.

# Where in CM is the Kerberos Security Realm value displayed?

You can find it in Settings menu in Administrator menubar, after that you should type the 'Kerberos Security Realm' in the serachfield and you will get the Security Realm.

# Which CDH service(s) host a property for enabling Kerberos authentication?

* HDFS
* MapReduce
* YARN
* Flume
* HBase
* Hive
* Hue
* Impala
* Oozie
* Pig
* Search
* Sentry
* Spark
* Sqoop
* Sqoop2
* Zookeeper
* Cloudera Manager

# How do you upgrade the CM agents?

First of all I stop the cluster, and after the services on cmd. I update the cloudera-manager-server and start it. If I refresh the CM in the browser, it will offer to upgrade the cloudera-agents.
(If you miss it after the server update, you will find the option on Hosts menu.)

# Give the tsquery statement used to chart Hue's CPU utilization?

```
SELECT cpu_user_rate, cpu_system_rate, (cpu_user_rate + cpu_system_rate) as 'Total CPU time'  WHERE roleType = HUE_SERVER
```

# Name all the roles that make up the Hive service

* Hive Metastore Server
* WebHCat
* HiveServer2
* Gateway

# What steps must be completed before integrating Cloudera Manager with Kerberos?

* Install the KDC on all hosts and openLDAP client on CM server. 
* In case of you use AD instead of MIT KDC, you have to enable the LDAPS protocol for Domain Controllers.
* Set the Kerberos to allow renewable tickets with non-zero ticket lifetimes. 
* Create an account, which allow for CM to create the other accounts in the KDC.