Before the Terasort suite:
`HADOOP_USER_NAME=hdfs hdfs dfs -mkdir /user/grcancelliere`
`HADOOP_USER_NAME=hdfs hdfs dfs -chown -R grcancelliere:grcancelliere /user/grcancelliere`

1. Teragen Command for `grcancelliere` user: `time hadoop jar /opt/cloudera/parcels/CDH/jars/hadoop-examples.jar teragen -Ddfs.blocksize=32m -Dmapred.map.tasks=4 107374183 teragen`
```
real    1m55.640s
user    2m13.411s
sys     0m6.632s
```

2. Terasort Command for `grcancelliere` user: `time hadoop jar /opt/cloudera/parcels/CDH/jars/hadoop-examples.jar terasort teragen terasort`

```
real    25m0.822s
user    11m11.650s
sys     1m7.093s
```

These values were obtained with the local job runner; after creating a YARN Gateway service the results are the following:

1. Teragen Command for `grcancelliere` user: `time hadoop jar /opt/cloudera/parcels/CDH/jars/hadoop-examples.jar teragen -Ddfs.blocksize=32m -Dmapred.map.tasks=4 107374183 teragen`

```
real    1m40.189s
user    0m6.700s
sys     0m0.370s
```

2. Terasort Command for `grcancelliere` user: `time hadoop jar /opt/cloudera/parcels/CDH/jars/hadoop-examples.jar terasort teragen terasort`

```
real    5m44.709s
user    0m9.051s
sys     0m0.536s
```