```
[raffles@sebcgrcm ~]$ kinit
Password for raffles@GRCANCELLIERE.SG:
[raffles@sebcgrcm ~]$ hdfs dfs -rm -r -f -skipTrash tgen512m
Deleted tgen512m
[raffles@sebcgrcm ~]$ hadoop jar /opt/cloudera/parcels/CDH/jars/hadoop-examples.jar terasort tgen512 tgen512m
18/10/19 09:21:46 INFO terasort.TeraSort: starting
18/10/19 09:21:47 INFO hdfs.DFSClient: Created token for raffles: HDFS_DELEGATION_TOKEN owner=raffles@GRCANCELLIERE.SG, renewer=yarn, realUser=, issueDate=1539940907608, maxDate=1540545707608, sequenceNumber=2, masterKeyId=2 on 10.0.0.4:8020
18/10/19 09:21:47 INFO security.TokenCache: Got dt for hdfs://sebcgrcm.westeurope.cloudapp.azure.com:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 10.0.0.4:8020, Ident: (token for raffles: HDFS_DELEGATION_TOKEN owner=raffles@GRCANCELLIERE.SG, renewer=yarn, realUser=, issueDate=1539940907608, maxDate=1540545707608, sequenceNumber=2, masterKeyId=2)
18/10/19 09:21:47 INFO input.FileInputFormat: Total input paths to process : 6
Spent 397ms computing base-splits.
Spent 3ms computing TeraScheduler splits.
Computing input splits took 400ms
Sampling 10 splits of 156
Making 8 from 100000 sampled records
Computing parititions took 657ms
Spent 1060ms computing partitions.
18/10/19 09:21:48 INFO client.RMProxy: Connecting to ResourceManager at sebcgrc1.westeurope.cloudapp.azure.com/10.0.0.5:8032
18/10/19 09:21:49 INFO mapreduce.JobSubmitter: number of splits:156
18/10/19 09:21:49 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1539940294414_0002
18/10/19 09:21:49 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 10.0.0.4:8020, Ident: (token for raffles: HDFS_DELEGATION_TOKEN owner=raffles@GRCANCELLIERE.SG, renewer=yarn, realUser=, issueDate=1539940907608, maxDate=1540545707608, sequenceNumber=2, masterKeyId=2)
18/10/19 09:21:50 INFO impl.YarnClientImpl: Submitted application application_1539940294414_0002
18/10/19 09:21:50 INFO mapreduce.Job: The url to track the job: http://sebcgrc1.westeurope.cloudapp.azure.com:8088/proxy/application_1539940294414_0002/
18/10/19 09:21:50 INFO mapreduce.Job: Running job: job_1539940294414_0002
18/10/19 09:21:58 INFO mapreduce.Job: Job job_1539940294414_0002 running in uber mode : false
18/10/19 09:21:58 INFO mapreduce.Job:  map 0% reduce 0%
18/10/19 09:22:07 INFO mapreduce.Job:  map 3% reduce 0%
18/10/19 09:22:12 INFO mapreduce.Job:  map 4% reduce 0%
18/10/19 09:22:13 INFO mapreduce.Job:  map 6% reduce 0%
18/10/19 09:22:18 INFO mapreduce.Job:  map 7% reduce 0%
18/10/19 09:22:19 INFO mapreduce.Job:  map 8% reduce 0%
18/10/19 09:22:20 INFO mapreduce.Job:  map 9% reduce 0%
18/10/19 09:22:21 INFO mapreduce.Job:  map 10% reduce 0%
18/10/19 09:22:22 INFO mapreduce.Job:  map 11% reduce 0%
18/10/19 09:22:26 INFO mapreduce.Job:  map 12% reduce 0%
18/10/19 09:22:28 INFO mapreduce.Job:  map 13% reduce 0%
18/10/19 09:22:31 INFO mapreduce.Job:  map 15% reduce 0%
18/10/19 09:22:37 INFO mapreduce.Job:  map 17% reduce 0%
18/10/19 09:22:39 INFO mapreduce.Job:  map 18% reduce 0%
18/10/19 09:22:42 INFO mapreduce.Job:  map 19% reduce 0%
18/10/19 09:22:44 INFO mapreduce.Job:  map 20% reduce 0%
18/10/19 09:22:46 INFO mapreduce.Job:  map 21% reduce 0%
18/10/19 09:22:50 INFO mapreduce.Job:  map 22% reduce 0%
18/10/19 09:22:51 INFO mapreduce.Job:  map 24% reduce 0%
18/10/19 09:22:52 INFO mapreduce.Job:  map 26% reduce 0%
18/10/19 09:22:56 INFO mapreduce.Job:  map 27% reduce 0%
18/10/19 09:22:58 INFO mapreduce.Job:  map 28% reduce 0%
18/10/19 09:22:59 INFO mapreduce.Job:  map 29% reduce 0%
18/10/19 09:23:00 INFO mapreduce.Job:  map 30% reduce 0%
18/10/19 09:23:01 INFO mapreduce.Job:  map 31% reduce 0%
18/10/19 09:23:02 INFO mapreduce.Job:  map 32% reduce 0%
18/10/19 09:23:04 INFO mapreduce.Job:  map 33% reduce 0%
18/10/19 09:23:07 INFO mapreduce.Job:  map 35% reduce 0%
18/10/19 09:23:08 INFO mapreduce.Job:  map 36% reduce 0%
18/10/19 09:23:09 INFO mapreduce.Job:  map 37% reduce 0%
18/10/19 09:23:11 INFO mapreduce.Job:  map 38% reduce 0%
18/10/19 09:23:12 INFO mapreduce.Job:  map 40% reduce 0%
18/10/19 09:23:13 INFO mapreduce.Job:  map 42% reduce 0%
18/10/19 09:23:17 INFO mapreduce.Job:  map 44% reduce 0%
18/10/19 09:23:18 INFO mapreduce.Job:  map 45% reduce 0%
18/10/19 09:23:20 INFO mapreduce.Job:  map 49% reduce 0%
18/10/19 09:23:23 INFO mapreduce.Job:  map 50% reduce 0%
18/10/19 09:23:24 INFO mapreduce.Job:  map 51% reduce 0%
18/10/19 09:23:25 INFO mapreduce.Job:  map 53% reduce 0%
18/10/19 09:23:27 INFO mapreduce.Job:  map 54% reduce 0%
18/10/19 09:23:28 INFO mapreduce.Job:  map 56% reduce 0%
18/10/19 09:23:29 INFO mapreduce.Job:  map 57% reduce 0%
18/10/19 09:23:30 INFO mapreduce.Job:  map 58% reduce 0%
18/10/19 09:23:33 INFO mapreduce.Job:  map 59% reduce 0%
18/10/19 09:23:34 INFO mapreduce.Job:  map 62% reduce 0%
18/10/19 09:23:36 INFO mapreduce.Job:  map 63% reduce 0%
18/10/19 09:23:37 INFO mapreduce.Job:  map 65% reduce 0%
18/10/19 09:23:39 INFO mapreduce.Job:  map 66% reduce 0%
18/10/19 09:23:41 INFO mapreduce.Job:  map 67% reduce 0%
18/10/19 09:23:42 INFO mapreduce.Job:  map 69% reduce 0%
18/10/19 09:23:44 INFO mapreduce.Job:  map 72% reduce 0%
18/10/19 09:23:46 INFO mapreduce.Job:  map 74% reduce 0%
18/10/19 09:23:49 INFO mapreduce.Job:  map 75% reduce 0%
18/10/19 09:23:51 INFO mapreduce.Job:  map 78% reduce 0%
18/10/19 09:23:53 INFO mapreduce.Job:  map 79% reduce 0%
18/10/19 09:23:54 INFO mapreduce.Job:  map 81% reduce 0%
18/10/19 09:23:57 INFO mapreduce.Job:  map 82% reduce 0%
18/10/19 09:23:58 INFO mapreduce.Job:  map 83% reduce 0%
18/10/19 09:23:59 INFO mapreduce.Job:  map 85% reduce 0%
18/10/19 09:24:00 INFO mapreduce.Job:  map 87% reduce 0%
18/10/19 09:24:02 INFO mapreduce.Job:  map 88% reduce 0%
18/10/19 09:24:03 INFO mapreduce.Job:  map 89% reduce 0%
18/10/19 09:24:07 INFO mapreduce.Job:  map 90% reduce 0%
18/10/19 09:24:09 INFO mapreduce.Job:  map 92% reduce 0%
18/10/19 09:24:11 INFO mapreduce.Job:  map 93% reduce 0%
18/10/19 09:24:13 INFO mapreduce.Job:  map 94% reduce 0%
18/10/19 09:24:14 INFO mapreduce.Job:  map 94% reduce 8%
18/10/19 09:24:15 INFO mapreduce.Job:  map 96% reduce 12%
18/10/19 09:24:16 INFO mapreduce.Job:  map 97% reduce 24%
18/10/19 09:24:19 INFO mapreduce.Job:  map 98% reduce 24%
18/10/19 09:24:20 INFO mapreduce.Job:  map 99% reduce 24%
18/10/19 09:24:21 INFO mapreduce.Job:  map 100% reduce 24%
18/10/19 09:24:22 INFO mapreduce.Job:  map 100% reduce 25%
18/10/19 09:24:26 INFO mapreduce.Job:  map 100% reduce 35%
18/10/19 09:24:27 INFO mapreduce.Job:  map 100% reduce 41%
18/10/19 09:24:28 INFO mapreduce.Job:  map 100% reduce 50%
18/10/19 09:24:29 INFO mapreduce.Job:  map 100% reduce 55%
18/10/19 09:24:30 INFO mapreduce.Job:  map 100% reduce 58%
18/10/19 09:24:32 INFO mapreduce.Job:  map 100% reduce 62%
18/10/19 09:24:33 INFO mapreduce.Job:  map 100% reduce 82%
18/10/19 09:24:34 INFO mapreduce.Job:  map 100% reduce 87%
18/10/19 09:24:35 INFO mapreduce.Job:  map 100% reduce 90%
18/10/19 09:24:36 INFO mapreduce.Job:  map 100% reduce 91%
18/10/19 09:24:37 INFO mapreduce.Job:  map 100% reduce 92%
18/10/19 09:24:39 INFO mapreduce.Job:  map 100% reduce 99%
18/10/19 09:24:41 INFO mapreduce.Job:  map 100% reduce 100%
18/10/19 09:24:42 INFO mapreduce.Job: Job job_1539940294414_0002 completed successfully
18/10/19 09:24:42 INFO mapreduce.Job: Counters: 50
        File System Counters
                FILE: Number of bytes read=2271506242
                FILE: Number of bytes written=4519959681
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=5120023244
                HDFS: Number of bytes written=5120000000
                HDFS: Number of read operations=492
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=16
        Job Counters
                Launched map tasks=156
                Launched reduce tasks=8
                Data-local map tasks=154
                Rack-local map tasks=2
                Total time spent by all maps in occupied slots (ms)=959486
                Total time spent by all reduces in occupied slots (ms)=253413
                Total time spent by all map tasks (ms)=959486
                Total time spent by all reduce tasks (ms)=253413
                Total vcore-milliseconds taken by all map tasks=959486
                Total vcore-milliseconds taken by all reduce tasks=253413
                Total megabyte-milliseconds taken by all map tasks=982513664
                Total megabyte-milliseconds taken by all reduce tasks=259494912
        Map-Reduce Framework
                Map input records=51200000
                Map output records=51200000
                Map output bytes=5222400000
                Map output materialized bytes=2223514105
                Input split bytes=23244
                Combine input records=0
                Combine output records=0
                Reduce input groups=51200000
                Reduce shuffle bytes=2223514105
                Reduce input records=51200000
                Reduce output records=51200000
                Spilled Records=102400000
                Shuffled Maps =1248
                Failed Shuffles=0
                Merged Map outputs=1248
                GC time elapsed (ms)=29546
                CPU time spent (ms)=602350
                Physical memory (bytes) snapshot=83707432960
                Virtual memory (bytes) snapshot=457913421824
                Total committed heap usage (bytes)=86426779648
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
        File Input Format Counters
                Bytes Read=5120000000
        File Output Format Counters
                Bytes Written=5120000000
18/10/19 09:24:42 INFO terasort.TeraSort: done
```