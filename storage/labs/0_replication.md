In order to make the replication work, I've made the following steps:

1. Modified `/etc/hosts` to add the IPs and the FQDNs for the cluster of my partner in each cluster VM;
2. Changed the HDFS property `dfs.client.use.datanode.hostname` to `true` in Cloudera Manager in order to force the resolution of the hostnames for the other cluster;
3. Edited the Azure Network Security Group to open the DistCP and Cloudera Manager ports (8020, 50010, 50070, 7180) to the Internet;
4. Registered the peer in BDR
5. Created a `Once` schedule to copy the teragen file `/hdfs_lab/gianfolo/unsorted/part-m-00000` into `/gianfolo`
6. Started the Schedule.

Results:

```
[grcancelliere@grcsebcm ~]$ HADOOP_USER_NAME=hdfs hdfs fsck /grcancelliere -files -blocks
Connecting to namenode via http://grcsebc1:50070/fsck?ugi=hdfs&files=1&blocks=1&path=%2Fgrcancelliere
FSCK started by hdfs (auth:SIMPLE) from /10.1.0.4 for path /grcancelliere at Tue Oct 16 11:07:52 UTC 2018
/grcancelliere <dir>
/grcancelliere/_SUCCESS 0 bytes, 0 block(s):  OK

/grcancelliere/part-m-00000 524288000 bytes, 4 block(s):  OK
0. BP-1164078471-10.1.0.7-1539681215517:blk_1073742554_1730 len=134217728 Live_repl=3
1. BP-1164078471-10.1.0.7-1539681215517:blk_1073742555_1731 len=134217728 Live_repl=3
2. BP-1164078471-10.1.0.7-1539681215517:blk_1073742557_1733 len=134217728 Live_repl=3
3. BP-1164078471-10.1.0.7-1539681215517:blk_1073742558_1734 len=121634816 Live_repl=3

Status: HEALTHY
 Total size:    524288000 B
 Total dirs:    1
 Total files:   2
 Total symlinks:                0
 Total blocks (validated):      4 (avg. block size 131072000 B)
 Minimally replicated blocks:   4 (100.0 %)
 Over-replicated blocks:        0 (0.0 %)
 Under-replicated blocks:       0 (0.0 %)
 Mis-replicated blocks:         0 (0.0 %)
 Default replication factor:    3
 Average block replication:     3.0
 Corrupt blocks:                0
 Missing replicas:              0 (0.0 %)
 Number of data-nodes:          3
 Number of racks:               1
FSCK ended at Tue Oct 16 11:07:52 UTC 2018 in 2 milliseconds


The filesystem under path '/grcancelliere' is HEALTHY
[grcancelliere@grcsebcm ~]$ HADOOP_USER_NAME=hdfs hdfs fsck /gianfolo -files -blocks
Connecting to namenode via http://grcsebc1:50070/fsck?ugi=hdfs&files=1&blocks=1&path=%2Fgianfolo
FSCK started by hdfs (auth:SIMPLE) from /10.1.0.4 for path /gianfolo at Tue Oct 16 11:09:15 UTC 2018
/gianfolo <dir>
/gianfolo/part-m-00000 524288000 bytes, 4 block(s):  OK
0. BP-1164078471-10.1.0.7-1539681215517:blk_1073742663_1839 len=134217728 Live_repl=3
1. BP-1164078471-10.1.0.7-1539681215517:blk_1073742664_1840 len=134217728 Live_repl=3
2. BP-1164078471-10.1.0.7-1539681215517:blk_1073742665_1841 len=134217728 Live_repl=3
3. BP-1164078471-10.1.0.7-1539681215517:blk_1073742666_1842 len=121634816 Live_repl=3

Status: HEALTHY
 Total size:    524288000 B
 Total dirs:    1
 Total files:   1
 Total symlinks:                0
 Total blocks (validated):      4 (avg. block size 131072000 B)
 Minimally replicated blocks:   4 (100.0 %)
 Over-replicated blocks:        0 (0.0 %)
 Under-replicated blocks:       0 (0.0 %)
 Mis-replicated blocks:         0 (0.0 %)
 Default replication factor:    3
 Average block replication:     3.0
 Corrupt blocks:                0
 Missing replicas:              0 (0.0 %)
 Number of data-nodes:          3
 Number of racks:               1
FSCK ended at Tue Oct 16 11:09:15 UTC 2018 in 0 milliseconds


The filesystem under path '/gianfolo' is HEALTHY
[grcancelliere@grcsebcm ~]$ hdfs dfs -ls /grcancelliere/
Found 2 items
-rw-r--r--   3 hdfs supergroup          0 2018-10-16 09:34 /grcancelliere/_SUCCESS
-rw-r--r--   3 hdfs supergroup  524288000 2018-10-16 09:34 /grcancelliere/part-m-00000
```