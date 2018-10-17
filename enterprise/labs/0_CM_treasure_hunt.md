* `What is ubertask optimization?`
The ubertask optimization runs "sufficiently small" jobs sequentially within a single JVM; how "small" is defined by the `mapreduce.job.ubertask.maxmaps`, `mapreduce.job.ubertask.maxreduces`, and `mapreduce.job.ubertask.maxbytes` properties.

* `Where in CM is the Kerberos Security Realm value displayed?`
The Kerberos Security Realm value is displayed in Administration/Settings, Kerberos category.

* `Which CDH service(s) host a property for enabling Kerberos authentication?`
In our current cluster the CDH services are Zookeeper, HDFS, YARN, Oozie, Hue, Hive, Activity Monitor, Cloudera Navigator, Reports Manager and Service Monitor.

* `How do you upgrade the CM agents?`
After upgrading the CM server, an upgrade wizard will show the steps to upgrade the CM agents. If you don't want to use the wizard you can update the Cloudera Repository for your OS, stop the agent, update the package and start the upgraded agent.

* `Give the `tsquery` statement used to chart Hue's CPU utilization?`
`select cpu_system_rate + cpu_user_rate where category=ROLE and serviceName=$SERVICENAME` with `$SERVICENAME = hive`

* `Name all the roles that make up the Hive service`
The roles are Gateway, WebHCat Server, Hive Metastore Server and HiveServer2.

* `What steps must be completed before integrating Cloudera Manager with Kerberos?`
1. Set up a working KDC. Cloudera Manager supports MIT KDC and Active Directory.
2. The KDC should be configured to have non-zero ticket lifetime and renewal lifetime. CDH will not work properly if tickets are not renewable.
3. OpenLdap client libraries should be installed on the Cloudera Manager Server host if you want to use Active Directory. Also, Kerberos client libraries should be installed on ALL hosts.
4. Cloudera Manager needs an account that has permissions to create other accounts in the KDC.