```
[fullerton@sebcgrcm ~]$ kinit
Password for fullerton@GRCANCELLIERE.SG:
[fullerton@sebcgrcm ~]$ hadoop jar /opt/cloudera/parcels/CDH/jars/hadoop-examples.jar pi
Usage: org.apache.hadoop.examples.QuasiMonteCarlo <nMaps> <nSamples>
Generic options supported are
-conf <configuration file>     specify an application configuration file
-D <property=value>            use value for given property
-fs <local|namenode:port>      specify a namenode
-jt <local|resourcemanager:port>    specify a ResourceManager
-files <comma separated list of files>    specify comma separated files to be copied to the map reduce cluster
-libjars <comma separated list of jars>    specify comma separated jar files to include in the classpath.
-archives <comma separated list of archives>    specify comma separated archives to be unarchived on the compute machines.

The general command line syntax is
bin/hadoop command [genericOptions] [commandOptions]

[fullerton@sebcgrcm ~]$ hadoop jar /opt/cloudera/parcels/CDH/jars/hadoop-examples.jar pi 10 1000
Number of Maps  = 10
Samples per Map = 1000
Wrote input for Map #0
Wrote input for Map #1
Wrote input for Map #2
Wrote input for Map #3
Wrote input for Map #4
Wrote input for Map #5
Wrote input for Map #6
Wrote input for Map #7
Wrote input for Map #8
Wrote input for Map #9
Starting Job
18/10/19 09:26:44 INFO client.RMProxy: Connecting to ResourceManager at sebcgrc1.westeurope.cloudapp.azure.com/10.0.0.5:8032
18/10/19 09:26:44 INFO hdfs.DFSClient: Created token for fullerton: HDFS_DELEGATION_TOKEN owner=fullerton@GRCANCELLIERE.SG, renewer=yarn, realUser=, issueDate=1539941204705, maxDate=1540546004705, sequenceNumber=3, masterKeyId=2 on 10.0.0.4:8020
18/10/19 09:26:44 INFO security.TokenCache: Got dt for hdfs://sebcgrcm.westeurope.cloudapp.azure.com:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 10.0.0.4:8020, Ident: (token for fullerton: HDFS_DELEGATION_TOKEN owner=fullerton@GRCANCELLIERE.SG, renewer=yarn, realUser=, issueDate=1539941204705, maxDate=1540546004705, sequenceNumber=3, masterKeyId=2)
18/10/19 09:26:44 INFO input.FileInputFormat: Total input paths to process : 10
18/10/19 09:26:45 INFO mapreduce.JobSubmitter: number of splits:10
18/10/19 09:26:45 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1539940294414_0003
18/10/19 09:26:45 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 10.0.0.4:8020, Ident: (token for fullerton: HDFS_DELEGATION_TOKEN owner=fullerton@GRCANCELLIERE.SG, renewer=yarn, realUser=, issueDate=1539941204705, maxDate=1540546004705, sequenceNumber=3, masterKeyId=2)
18/10/19 09:26:45 INFO impl.YarnClientImpl: Submitted application application_1539940294414_0003
18/10/19 09:26:45 INFO mapreduce.Job: The url to track the job: http://sebcgrc1.westeurope.cloudapp.azure.com:8088/proxy/application_1539940294414_0003/
18/10/19 09:26:45 INFO mapreduce.Job: Running job: job_1539940294414_0003
18/10/19 09:26:52 INFO mapreduce.Job: Job job_1539940294414_0003 running in uber mode : false
18/10/19 09:26:52 INFO mapreduce.Job:  map 0% reduce 0%
18/10/19 09:26:58 INFO mapreduce.Job:  map 20% reduce 0%
18/10/19 09:26:59 INFO mapreduce.Job:  map 30% reduce 0%
18/10/19 09:27:02 INFO mapreduce.Job:  map 60% reduce 0%
18/10/19 09:27:03 INFO mapreduce.Job:  map 100% reduce 0%
18/10/19 09:27:08 INFO mapreduce.Job:  map 100% reduce 100%
18/10/19 09:27:09 INFO mapreduce.Job: Job job_1539940294414_0003 completed successfully
18/10/19 09:27:09 INFO mapreduce.Job: Counters: 50
        File System Counters
                FILE: Number of bytes read=106
                FILE: Number of bytes written=1663349
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=2970
                HDFS: Number of bytes written=215
                HDFS: Number of read operations=43
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=3
        Job Counters
                Launched map tasks=10
                Launched reduce tasks=1
                Data-local map tasks=9
                Rack-local map tasks=1
                Total time spent by all maps in occupied slots (ms)=63695
                Total time spent by all reduces in occupied slots (ms)=2608
                Total time spent by all map tasks (ms)=63695
                Total time spent by all reduce tasks (ms)=2608
                Total vcore-milliseconds taken by all map tasks=63695
                Total vcore-milliseconds taken by all reduce tasks=2608
                Total megabyte-milliseconds taken by all map tasks=65223680
                Total megabyte-milliseconds taken by all reduce tasks=2670592
        Map-Reduce Framework
                Map input records=10
                Map output records=20
                Map output bytes=180
                Map output materialized bytes=340
                Input split bytes=1790
                Combine input records=0
                Combine output records=0
                Reduce input groups=2
                Reduce shuffle bytes=340
                Reduce input records=20
                Reduce output records=0
                Spilled Records=40
                Shuffled Maps =10
                Failed Shuffles=0
                Merged Map outputs=10
                GC time elapsed (ms)=1257
                CPU time spent (ms)=7300
                Physical memory (bytes) snapshot=4895531008
                Virtual memory (bytes) snapshot=30713200640
                Total committed heap usage (bytes)=4871159808
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
        File Input Format Counters
                Bytes Read=1180
        File Output Format Counters
                Bytes Written=97
Job Finished in 24.753 seconds
Estimated value of Pi is 3.14080000000000000000
```