```
[grcancelliere@grcsebcm ~]$ hdfs dfs -mkdir /user/grcancelliere/precious
[grcancelliere@grcsebcm ~]$ hdfs dfs -put SEBC-master.zip /user/grcancelliere/precious
[grcancelliere@grcsebcm ~]$ hdfs dfsadmin -allowSnapshot /user/grcancelliere/precious
Allowing snaphot on /user/grcancelliere/precious succeeded
[grcancelliere@grcsebcm ~]$ hdfs dfs -createSnapshot /user/grcancelliere/precious sebc-hdfs-test
Created snapshot /user/grcancelliere/precious/.snapshot/sebc-hdfs-test
[grcancelliere@grcsebcm ~]$ hdfs dfs -rm -r -f -skipTrash /user/grcancelliere/precious
rm: The directory /user/grcancelliere/precious cannot be deleted since /user/grcancelliere/precious is snapshottable and already has snapshots
[grcancelliere@grcsebcm ~]$ hdfs dfs -rm -skipTrash /user/grcancelliere/precious/SEBC-master.zip
Deleted /user/grcancelliere/precious/SEBC-master.zip
[grcancelliere@grcsebcm ~]$ hdfs dfs -cp /user/grcancelliere/precious/.snapshot/sebc-hdfs-test/SEBC-master.zip /user/grcancelliere/precious/
```