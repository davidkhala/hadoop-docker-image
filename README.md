# hadoop-docker-image
Keep it LTS. An Apache Hadoop docker image


## Current LTS lines
- 3
    - 3.1
    - 3.2
    - 3.3
- 2
    - 2.10


## Apache Hadoop Container Support is NOT off-the-shelf
https://cwiki.apache.org/confluence/display/HADOOP/Container+support
- They are base images without entry-point executable
## DockerHub `apache/hadoop:2`
- Java
    - `openjdk version "1.8.0_201"`
    - $JAVA_HOME=/usr/lib/jvm/jre/
- Path
    - Extra Path: `/opt/hadoop/bin`
    - Working directory: `/opt/hadoop`, it can be $HADOOP_HOME
    - Config directory: `/opt/hadoop/etc/hadoop`
## Configuration
- Use environments to control config than XML
    - https://stackoverflow.com/questions/22332760/how-can-i-specify-hadoop-xml-configuration-variables-via-the-hadoop-shell-script
    - `export HADOOP_OPTS="$HADOOP_OPTS -Ddfs.name.dir=$NAMENODE_DATA -Ddfs.data.dir=$DFS_DATA"`
    - exist configs
        - fs.defaultFS          hdfs://hadoop-master:9000/
        - dfs.namenode.name.dir file:///root/hdfs/namenode (not exist, you should make dir)
        - dfs.datanode.data.dir file:///root/hdfs/datanode
        - dfs.replication       2
        - mapreduce.framework.name      yarn
        - yarn.nodemanager.aux-services mapreduce_shuffle
        - yarn.nodemanager.aux-services.mapreduce_shuffle.class org.apache.hadoop.mapred.ShuffleHandler
        - yarn.resourcemanager.hostname hadoop-master

## Credits
- [kiwenlau: hadoop-cluster-docker](https://github.com/kiwenlau/hadoop-cluster-docker)
