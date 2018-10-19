* `Command and output for` hdfs dfs -ls /user
```
[sebc@sebcgrcm ~]$ hdfs dfs -ls /user
Found 6 items
drwxr-xr-x   - fullerton fullerton          0 2018-10-19 08:29 /user/fullerton
drwxrwxrwx   - mapred    hadoop             0 2018-10-19 08:24 /user/history
drwxrwxr-t   - hive      hive               0 2018-10-19 08:25 /user/hive
drwxrwxr-x   - hue       hue                0 2018-10-19 08:25 /user/hue
drwxrwxr-x   - oozie     oozie              0 2018-10-19 08:25 /user/oozie
drwxr-xr-x   - raffles   raffles            0 2018-10-19 08:29 /user/raffles
```
* `The output from the CM API call` ../api/v14/hosts
```
[sebc@sebcgrcm ~]$ curl -u admin:admin 'http://sebcgrc1:7180/api/v14/hosts'
{
  "items" : [ {
    "hostId" : "f2c458be-510f-4ad6-9bb9-50ef63b71119",
    "ipAddress" : "10.0.0.5",
    "hostname" : "sebcgrc1.westeurope.cloudapp.azure.com",
    "rackId" : "/default",
    "hostUrl" : "http://sebcgrc1.westeurope.cloudapp.azure.com:7180/cmf/hostRedirect/f2c458be-510f-4ad6-9bb9-50ef63b71119",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 14697304064
  }, {
    "hostId" : "589fda1d-341e-400d-a7eb-0daf1e2eae1d",
    "ipAddress" : "10.0.0.6",
    "hostname" : "sebcgrc2.westeurope.cloudapp.azure.com",
    "rackId" : "/default",
    "hostUrl" : "http://sebcgrc1.westeurope.cloudapp.azure.com:7180/cmf/hostRedirect/589fda1d-341e-400d-a7eb-0daf1e2eae1d",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 14697304064
  }, {
    "hostId" : "3c85da3c-abad-463a-825d-0c3dc69556e7",
    "ipAddress" : "10.0.0.7",
    "hostname" : "sebcgrc3.westeurope.cloudapp.azure.com",
    "rackId" : "/default",
    "hostUrl" : "http://sebcgrc1.westeurope.cloudapp.azure.com:7180/cmf/hostRedirect/3c85da3c-abad-463a-825d-0c3dc69556e7",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 14697304064
  }, {
    "hostId" : "eb0ff39a-5b84-4461-a717-740b03e886f5",
    "ipAddress" : "10.0.0.8",
    "hostname" : "sebcgrc4.westeurope.cloudapp.azure.com",
    "rackId" : "/default",
    "hostUrl" : "http://sebcgrc1.westeurope.cloudapp.azure.com:7180/cmf/hostRedirect/eb0ff39a-5b84-4461-a717-740b03e886f5",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 14697304064
  }, {
    "hostId" : "75b16d7e-2e9b-4e31-9d99-8d646d652cf5",
    "ipAddress" : "10.0.0.4",
    "hostname" : "sebcgrcm.westeurope.cloudapp.azure.com",
    "rackId" : "/default",
    "hostUrl" : "http://sebcgrc1.westeurope.cloudapp.azure.com:7180/cmf/hostRedirect/75b16d7e-2e9b-4e31-9d99-8d646d652cf5",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 14697304064
  } ]
}
```