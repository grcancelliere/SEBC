* `Report the latest available version of the API`
```
[grcancelliere@grcsebcm ~]$ curl -u grcancelliere:cloudera 'http://grcsebcm:7180/api/version'
v19
```

* `Report the CM version`
```
[grcancelliere@grcsebcm ~]$ curl -u grcancelliere:cloudera 'http://grcsebcm:7180/api/v19/cm/version'
{
  "version" : "5.14.4",
  "buildUser" : "jenkins",
  "buildTimestamp" : "20180707-0445",
  "gitHash" : "0971e84bdceb60db9b96533f46451f40ed8cbdf9",
  "snapshot" : false
}
```

* `List all CM users`
```
[grcancelliere@grcsebcm ~]$ curl -u grcancelliere:cloudera 'http://grcsebcm:7180/api/v19/users'
{
  "items" : [ {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ]
  }, {
    "name" : "grcancelliere",
    "roles" : [ "ROLE_ADMIN" ]
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ]
  } ]
}
```

* `Report the database server in use by CM`
```
[grcancelliere@grcsebcm ~]$ curl -u grcancelliere:cloudera 'http://grcsebcm:7180/api/v19/cm/scmDbInfo'
{
  "scmDbType" : "MYSQL",
  "embeddedDbUsed" : false
}
```