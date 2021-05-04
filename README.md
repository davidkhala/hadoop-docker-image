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
### DockerHub `apache/hadoop:3`
- Java
    - `openjdk version "1.8.0_212"`
    - $JAVA_HOME=/usr/lib/jvm/jre/
- Path
    - Extra Path: `/opt/hadoop/bin`
    - Working directory: `/opt/hadoop`, it can be $HADOOP_HOME
    - Config directory: `/opt/hadoop/etc/hadoop`

## Credits
- [kiwenlau: hadoop-cluster-docker](https://github.com/kiwenlau/hadoop-cluster-docker)
