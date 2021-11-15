# Kafka_Doc

Step 1: Download and Install Java JDK 1.8.
Step 2:
2.1:  Download Apache Kafka from official website in binary version and extract on c-drive it’s looks like as below
 
2.2. Now we need to consider ZooKeeper and Kafka Properties files and make any changes if we need. For example, if we need to specify any custom locations to store logs and data instead of default temp folders, we can do that. Let’s create a data folder inside our Kafka folder and inside that creates separate folders for Kafka and ZooKeeper to store Kafka logs and ZooKeeper data respectively. 
 
2.3. Now, we need to update configuration files to point to these newly created directories. To update Kafka configurations, open server.properties file and change logs location to newly created directory as below:
log.dirs=D:/kafka-2.6.0/data/kafka
Similarly, we need to change data directory for ZooKeeper by updating Zookeeper.properties file as below:
dataDir= D:/kafka-2.6.0/data/zookeeper
3. Running kafka in windows
First we need to run zookeeper server by using below command
C:\kafka_2.12-2.8.1>.\bin\windows\zookeeper-server-start.bat .\config\zookeeper.properties
Second run kafka server by using below command
C:\kafka_2.12-2.8.1>.\bin\windows\kafka-server-start.bat .\config\server.properties
4. Open new command prompt and create topic using below command
C:\kafka_2.12-2.8.1>.\bin\windows\kafka-topics.bat --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic test
Check topic is created or not using following command
C:\kafka_2.12-2.8.1>.\bin\windows\kafka-topics.bat -list --zookeeper localhost:2181
