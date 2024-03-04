# UoM_MapReduce-vs-Spark

The basics of big data processing using MapReduce and Apache Spark, two popular technologies in the industry.

## 1. Create S3 Bucket Structure

Create an S3 bucket with the following file structure:

![S3 Bucket](<images/s3-bucket.png>)

## 2. Create EMR Cluster

- Create an EMR cluster with Spark 2.4.0, ensuring Hive is present.
- Add two Worker nodes and Task nodes.
- The cluster should be in a "Waiting" status.
- Enable SSH connection for the Master Node by adding a new rule for SSH, with the Type set to “SSH” and Source to “My-IP”.
- Remotely connect to the cluster using Putty.

![EMR Cluster](<images/emr-cluster.png>)
![Remotely Connect to the Cluster](<images/remotely connect ssh.PNG>)

## 3. Process Data using Apache Spark

After configuring the EMR cluster, load data into it and process using Apache Spark.
- Transform and analyze data using the Spark framework.
- Access the Spark framework by entering the `spark-shell` command.

![Open Spark Shell](<images/spark-login.PNG>)

- Load the data from the CSV into HDFS, partition the data for parallel processing based on the column `c1` or the year column, and store that partitioned data in the chosen S3 bucket location.
- View the partitioned data.

![View Data](<images/partition_by_year_c1.PNG>)
![S3 Bucket Partitions](<images/partition_by_year_s3.png>)

- Apply SQL queries to the data. Run the command shown below and see the output with query processing time. For example, calculating the average carrier delay.

![SQL Query Example](<images/spark-query.PNG>)

## 4. Process Data using Hadoop MapReduce

Start loading data into the EMR cluster and process using Hadoop MapReduce.
- Run the command `hive` as shown below and create a Hive table that points to the S3 location of your data.
- Run HiveQL queries to analyze and process the data in our table. For example, calculating average carrier delay.

![HiveQL Query Example](<images/hadoop-query.PNG>)


## 5. Assignment Results
### Query Execution Time Comparison (Running Time vs Iteration)

Run the query using Hadoop and Spark for 5 times and plot the graph comparing both methods.

#### 1. Year Wise Carrier Delay from 2003-2010
![Carrier Delay](<images/comparison_plot_average carrier delay.png>)

#### 2. Year Wise NAS Delay from 2003-2010
![NAS Delay](<images/comparison_plot_average nas delay.png>)

#### 3. Year Wise Weather Delay from 2003-2010
![Weather Delay](<images/comparison_plot_average weather delay.png>)

#### 4. Year Wise Late Aircraft Delay from 2003-2010
![Late Aircraft Delay](<images/comparison_plot_average late aircraft delay.png>)

#### 5. Year Wise Security Delay from 2003-2010
![Security Delay](<images/comparison_plot_average security delay.png>)

### Average Execution Time Comparison

Calculate the average time taken by MapReduce and Spark for each query and plot the graph.

![Average Execution Time](<images/total average time and delays.png>)

