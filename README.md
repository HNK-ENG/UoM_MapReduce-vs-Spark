# UoM_MapReduce-vs-Spark

The basics of big data processing using MapReduce and Apache Spark, two popular technologies in the industry.

## 1. Create S3 Bucket Structure

Create an S3 bucket with the following file structure:

![S3 Bucket](<images\s3-bucket.png>)

## 2. Create EMR Cluster

- Create an EMR cluster with Spark 2.4.0, ensuring Hive is present.
- Add two Worker nodes and Task nodes.
- The cluster should be in a "Waiting" status.
- Enable SSH connection for the Master Node by adding a new rule for SSH, with the Type set to “SSH” and Source to “My-IP”.
- Remotely connect to the cluster using Putty.

![EMR Cluster](<images\emr-cluster.png>)
![Remotely Connect to the Cluster](<images\remotely connect ssh.PNG>)

## 3. Process Data using Apache Spark

After configuring the EMR cluster, load data into it and process using Apache Spark.
- Transform and analyze data using the Spark framework.
- Access the Spark framework by entering the `spark-shell` command.

![Open Spark Shell](<link to png of opening spark-shell>)

- Load the data from the CSV into HDFS, partition the data for parallel processing based on the column `c1` or the year column, and store that partitioned data in the chosen S3 bucket location.

![Partition Data](<link to pngs for that>)

- View the partitioned data.

![View Data](<link to png for that>)
![S3 Bucket Partitions](<link to s3 bucket partitions as well>)

- Apply SQL queries to the data. Run the command shown below and see the output with query processing time. For example, calculating the average carrier delay.

![SQL Query Example](<link to png of one example>)

## 4. Process Data using Hadoop MapReduce

Start loading data into the EMR cluster and process using Hadoop MapReduce.
- Run the command `hive` as shown below and create a Hive table that points to the S3 location of your data.

![Hive Command](<link to png of that>)

- Run HiveQL queries to analyze and process the data in our table. For example, calculating average carrier delay.

![HiveQL Query Example](<link to png of that>)
