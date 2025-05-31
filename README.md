# Big_Data_EX_02

# EX_02 - INSTALL, CONFIGURE AND RUN HADOOP AND HDFS

## Aim:

To install, configure, and run Hadoop and its distributed file system (HDFS) on a single-node cluster, and to understand its basic functionalities such as storing files and running sample jobs.

## Requirements:

1. Ubuntu/Linux system

2. Java (JDK 11 or later)

3. Hadoop (latest stable version)

4. Internet connection

5. Terminal access

## Algorithm:

1. Install Java and Hadoop:
   
   - Install Java (JDK 11 or higher) and download the Hadoop binary from the official Apache website.

2. Set Environment Variables:
   
   - Configure environment variables for JAVA_HOME, HADOOP_HOME, and update the system PATH.

3. Configure Hadoop Files:
   
   - Edit the core Hadoop configuration files (core-site.xml, hdfs-site.xml, mapred-site.xml, yarn-site.xml) to set up NameNode, DataNode, and MapReduce framework.

4. Format NameNode and Start Services:
   
   - Format the Hadoop NameNode and start HDFS (start-dfs.sh) and YARN (start-yarn.sh) services.

5. Run Sample HDFS Commands and Job:
   
   - Create directories, upload a file to HDFS, and run a sample MapReduce job (e.g., WordCount) to verify successful setup.

## Program:
```
DEVELOPED BY : NIRAUNJANA GAYATHRI G R
REGISTER NO. : 212222230096
```
```
# Step 1: Install Java
sudo apt update
sudo apt install openjdk-11-jdk -y
java -version

# Step 2: Set JAVA_HOME
echo "export JAVA_HOME=/usr/lib/jvm/java-11-openjdk-amd64" >> ~/.bashrc
echo "export PATH=\$JAVA_HOME/bin:\$PATH" >> ~/.bashrc
source ~/.bashrc

# Step 3: Extract Hadoop and set environment variables
tar -xvzf hadoop-X.Y.Z.tar.gz
sudo mv hadoop-X.Y.Z /usr/local/hadoop
echo "export HADOOP_HOME=/usr/local/hadoop" >> ~/.bashrc
echo "export PATH=\$HADOOP_HOME/bin:\$HADOOP_HOME/sbin:\$PATH" >> ~/.bashrc
echo "export HADOOP_CONF_DIR=\$HADOOP_HOME/etc/hadoop" >> ~/.bashrc
source ~/.bashrc

# Step 4: Format the NameNode
hdfs namenode -format

# Step 5: Start HDFS and YARN
start-dfs.sh
start-yarn.sh

# Step 6: Create a directory in HDFS and test file operations
hdfs dfs -mkdir /user
hdfs dfs -mkdir /user/niraunjana
hdfs dfs -put localfile.txt /user/niraunjana/
hdfs dfs -ls /user/niraunjana

# Step 7: Run a sample MapReduce job (e.g., WordCount)
hadoop jar $HADOOP_HOME/share/hadoop/mapreduce/hadoop-mapreduce-examples-X.Y.Z.jar wordcount /user/niraunjana/input /user/niraunjana/output
hdfs dfs -cat /user/niraunjana/output/part-r-00000
```

## Output:

![image](https://github.com/user-attachments/assets/b794618b-0630-4869-b36e-71650dff2265)


![image](https://github.com/user-attachments/assets/98227c79-3be3-4ce1-bef4-c814bf478ce4)


![image](https://github.com/user-attachments/assets/0fa4d331-8ef2-42c6-b3e3-bd21b9b29b7f)


![image](https://github.com/user-attachments/assets/0d18c833-7532-4bc7-94d7-2617f7530d17)


![image](https://github.com/user-attachments/assets/8e3d3b44-0a10-4a68-9c1e-aba2c2fc9f35)


## Result:

Hadoop and HDFS were successfully installed and configured. HDFS was used to store data, and a MapReduce job (WordCount) was executed successfully, demonstrating basic Hadoop functionality.
