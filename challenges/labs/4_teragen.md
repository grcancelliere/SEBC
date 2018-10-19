* `The full teragen command`
```
[raffles@sebcgrcm ~]$ time hadoop jar /opt/cloudera/parcels/CDH/jars/hadoop-examples.jar teragen -Ddfs.blocksize=32m -Dmapreduce.job.maps=6 51200000 tgen512
```
* `The output of the` time `command`
```
18/10/19 08:47:59 INFO client.RMProxy: Connecting to ResourceManager at sebcgrc1.westeurope.cloudapp.azure.com/10.0.0.5:8032
18/10/19 08:47:59 INFO terasort.TeraGen: Generating 51200000 using 6
18/10/19 08:48:00 INFO mapreduce.JobSubmitter: number of splits:6
18/10/19 08:48:00 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1539937456808_0003
18/10/19 08:48:00 INFO impl.YarnClientImpl: Submitted application application_1539937456808_0003
18/10/19 08:48:00 INFO mapreduce.Job: The url to track the job: http://sebcgrc1.westeurope.cloudapp.azure.com:8088/proxy/application_1539937456808_0003/
18/10/19 08:48:00 INFO mapreduce.Job: Running job: job_1539937456808_0003
18/10/19 08:48:06 INFO mapreduce.Job: Job job_1539937456808_0003 running in uber mode : false
18/10/19 08:48:06 INFO mapreduce.Job:  map 0% reduce 0%
18/10/19 08:48:22 INFO mapreduce.Job:  map 16% reduce 0%
18/10/19 08:48:23 INFO mapreduce.Job:  map 45% reduce 0%
18/10/19 08:48:28 INFO mapreduce.Job:  map 54% reduce 0%
18/10/19 08:48:29 INFO mapreduce.Job:  map 69% reduce 0%
18/10/19 08:48:34 INFO mapreduce.Job:  map 73% reduce 0%
18/10/19 08:48:35 INFO mapreduce.Job:  map 77% reduce 0%
18/10/19 08:48:40 INFO mapreduce.Job:  map 90% reduce 0%
18/10/19 08:48:41 INFO mapreduce.Job:  map 98% reduce 0%
18/10/19 08:48:43 INFO mapreduce.Job:  map 100% reduce 0%
18/10/19 08:48:45 INFO mapreduce.Job: Job job_1539937456808_0003 completed successfully
18/10/19 08:48:46 INFO mapreduce.Job: Counters: 31
        File System Counters
                FILE: Number of bytes read=0
                FILE: Number of bytes written=897198
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=511
                HDFS: Number of bytes written=5120000000
                HDFS: Number of read operations=24
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=12
        Job Counters
                Launched map tasks=6
                Other local map tasks=6
                Total time spent by all maps in occupied slots (ms)=210752
                Total time spent by all reduces in occupied slots (ms)=0
                Total time spent by all map tasks (ms)=210752
                Total vcore-milliseconds taken by all map tasks=210752
                Total megabyte-milliseconds taken by all map tasks=215810048
        Map-Reduce Framework
                Map input records=51200000
                Map output records=51200000
                Input split bytes=511
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=1107
                CPU time spent (ms)=76200
                Physical memory (bytes) snapshot=2247290880
                Virtual memory (bytes) snapshot=16727633920
                Total committed heap usage (bytes)=2185232384
        org.apache.hadoop.examples.terasort.TeraGen$Counters
                CHECKSUM=109963291816450258
        File Input Format Counters
                Bytes Read=0
        File Output Format Counters
                Bytes Written=5120000000

real    0m48.977s
user    0m6.726s
sys     0m0.407s
```
* `The command and output of` hdfs dfs -ls /user/raffles/tgen512
```
[sebc@sebcgrcm ~]$ hdfs dfs -ls /user/raffles/tgen512
Found 7 items
-rw-r--r--   3 raffles raffles          0 2018-10-19 08:40 /user/raffles/tgen512/_SUCCESS
-rw-r--r--   3 raffles raffles  853333400 2018-10-19 08:40 /user/raffles/tgen512/part-m-00000
-rw-r--r--   3 raffles raffles  853333300 2018-10-19 08:40 /user/raffles/tgen512/part-m-00001
-rw-r--r--   3 raffles raffles  853333300 2018-10-19 08:40 /user/raffles/tgen512/part-m-00002
-rw-r--r--   3 raffles raffles  853333400 2018-10-19 08:40 /user/raffles/tgen512/part-m-00003
-rw-r--r--   3 raffles raffles  853333300 2018-10-19 08:40 /user/raffles/tgen512/part-m-00004
-rw-r--r--   3 raffles raffles  853333300 2018-10-19 08:40 /user/raffles/tgen512/part-m-00005
```
* `Show how many blocks are associated with this directory`
```
[sebc@sebcgrcm ~]$ hdfs fsck /user/raffles/tgen512 | grep 'Total blocks'
Connecting to namenode via http://sebcgrcm.westeurope.cloudapp.azure.com:50070/fsck?ugi=sebc&path=%2Fuser%2Fraffles%2Ftgen512
 Total blocks (validated):      156 (avg. block size 32820512 B)
```