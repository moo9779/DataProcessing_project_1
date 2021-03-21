Byungmoo Brian Kim
K=1: 8 trials 
count:1
(505336095this_is_a_bitcoin_block_of_89168016,0987c2b1dce39039290a14af2ed2cca09269d8f0abea6b916f8ff611f93730da)
Time elapsed:1s

K=2: 199 trials
count:1
(977473664this_is_a_bitcoin_block_of_89168016,002677bd49654eaedd57ae4a3b3228b19cd269cf4c24081ac112d2927926da23)
Time elapsed:1s

K=3: 3443 trials
count:1
(530018090this_is_a_bitcoin_block_of_89168016,000ec272065a65a2245e4f2a62cd170de69eeda9ebca5b2ef253674e4c52dcd0)
Time elapsed:1s

K=4 9999 trials
count:1
(1215490459this_is_a_bitcoin_block_of_89168016,0000115f68ae411fc0cfda656b23ed7d617149fda852bb21f2fb5de22b32367c)
Time elapsed:1s

K=5 199,995 trials
count:1
(710458548this_is_a_bitcoin_block_of_89168016,00000a2a7ab1eef052c7d1bb78c2237ab501eebd4f1da2a0d3993545b6c0ea7d)
Time elapsed:1s

K=6 7398986 trials
count:1
(1523871716this_is_a_bitcoin_block_of_89168016,0000008e1922778b0e96f4cf36374fd32cec1d4b2d0e3d354136e2768d22147b)
Time elapsed:4s
 
K=7 300000000 trials
found. count:1
(1331697934this_is_a_bitcoin_block_of_89168016,000000050c1728c8d6b044e3493edba960579d06ebb39a9403d2b82e0b451cd9)
Time elapsed:1125s,18 min 51 sec
4 cores, standard core, 500Gb disk storage, 2 worker nodes, 

capacity-scheduler:yarn.scheduler.capacity.root.default.ordering-policy:fair
core:fs.gs.block.size:134217728
core:fs.gs.metadata.cache.enable:false
core:hadoop.ssl.enabled.protocols:TLSv1,TLSv1.1,TLSv1.2
distcp:mapreduce.map.java.opts:-Xmx768m
distcp:mapreduce.map.memory.mb:1024
distcp:mapreduce.reduce.java.opts:-Xmx768m
distcp:mapreduce.reduce.memory.mb:1024
hadoop-env:HADOOP_DATANODE_OPTS:-Xmx512m
hdfs:dfs.datanode.address:0.0.0.0:9866
hdfs:dfs.datanode.http.address:0.0.0.0:9864
hdfs:dfs.datanode.https.address:0.0.0.0:9865
hdfs:dfs.datanode.ipc.address:0.0.0.0:9867
hdfs:dfs.namenode.handler.count:20
hdfs:dfs.namenode.http-address:0.0.0.0:9870
hdfs:dfs.namenode.https-address:0.0.0.0:9871
hdfs:dfs.namenode.lifeline.rpc-address:kimcjo-3390-cluster-m:8050
hdfs:dfs.namenode.secondary.http-address:0.0.0.0:9868
hdfs:dfs.namenode.secondary.https-address:0.0.0.0:9869
hdfs:dfs.namenode.service.handler.count:10
hdfs:dfs.namenode.servicerpc-address:kimcjo-3390-cluster-m:8051
hive:hive.fetch.task.conversion:none
mapred-env:HADOOP_JOB_HISTORYSERVER_HEAPSIZE:3840
mapred:mapreduce.job.maps:21
mapred:mapreduce.job.reduce.slowstart.completedmaps:0.95
mapred:mapreduce.job.reduces:7
mapred:mapreduce.jobhistory.recovery.store.class:org.apache.hadoop.mapreduce.v2.hs.HistoryServerLeveldbStateStoreService
mapred:mapreduce.map.cpu.vcores:1
mapred:mapreduce.map.java.opts:-Xmx2524m
mapred:mapreduce.map.memory.mb:3156
mapred:mapreduce.reduce.cpu.vcores:1
mapred:mapreduce.reduce.java.opts:-Xmx2524m
mapred:mapreduce.reduce.memory.mb:3156
mapred:mapreduce.task.io.sort.mb:256
mapred:yarn.app.mapreduce.am.command-opts:-Xmx2524m
mapred:yarn.app.mapreduce.am.resource.cpu-vcores:1
mapred:yarn.app.mapreduce.am.resource.mb:3156
spark-env:SPARK_DAEMON_MEMORY:3840m
spark:spark.driver.maxResultSize:1920m
spark:spark.driver.memory:3840m
spark:spark.executor.cores:2
spark:spark.executor.instances:2
spark:spark.executor.memory:5739m
spark:spark.executorEnv.OPENBLAS_NUM_THREADS:1
spark:spark.scheduler.mode:FAIR
spark:spark.sql.cbo.enabled:true
spark:spark.ui.port:0
spark:spark.yarn.am.memory:640m
yarn-env:YARN_NODEMANAGER_HEAPSIZE:1536
yarn-env:YARN_RESOURCEMANAGER_HEAPSIZE:3840
yarn-env:YARN_TIMELINESERVER_HEAPSIZE:3840
yarn:yarn.nodemanager.address:0.0.0.0:8026
yarn:yarn.nodemanager.resource.cpu-vcores:4
yarn:yarn.nodemanager.resource.memory-mb:12624
yarn:yarn.resourcemanager.nodemanager-graceful-decommission-timeout-secs:86400
yarn:yarn.scheduler.maximum-allocation-mb:12624
yarn:yarn.scheduler.minimum-allocation-mb:1


My process for estimating the number of trials was incrementing by 5,000,000. K=6 had 7398986 trials, so I started at 10,000,000 trials. Then, I incremented by 5,000,000 and the times went from 5 minutes to 7,12, 15, 17 and 18 minutes for 10M, 15M, 20M, 25M and 30M trials respectively. At 25 million, it still said there was no match so when I got one match at 30M I stopped. Since I got 1 match and each job was taking 15-20 minutes, I stopped at 30M.


Part c:
I believe that this is more efficient than generating random numbers because with random numbers, there is no set limit with how many times it could take. If there are 100 trials, it could find it 10 times or 1 time, all based on randomness. If there was a program that generated the potential nonce instead of randomly creating it, then at least there would be consistency with the results, making it more efficient. If it were done randomly, there would be consistency and thus making it more inefficient and in the long run, create more work for the cpu, cores and nodes.
