# spark

# Getting Started with Spark 2
* Spark 1.x was already a great general purpose computing engine
* Spark 2.x takes it to a new level in several ways.
* 2nd generation Tungsten engine provides 10x-100x performance improvement
* Unified APIs Datasets, DataFrames and Spark SQL
* Higher Level ML APIs
* Unified batch and streaming queries

# Spark Intro
* Spark is built on top of Hadoop spesifically YARN and HDFS.
* Once the task has been defined, this will be run as a job by the Cluster Manager. YARN, Apache Mesos or Standalone.
![alt text](http://url/to/img.png)

# RDD
* All operations in Spark are performed in-memory objects.
* An RDD is a collection of records.

### RDD Characteristics
###### Partitioned
* Split across data node on cluster. Data is divided into partitions. Distributed to multiple machines.
Process occurs on nodes parallel. Data is stored in memory for each node in cluster.
###### Immutable
* Once RDD created, can not be changed, edited or etc. read-only. Can not be mutated. Only two operations allowed to perform on RDD. 
* Transformation: transform into another RDD. Example: Load data, pick only 3rd column, sort the values.<br/>
**Tranformations are executed only when a result is request. (action performed)** 
* Lazy Evaluation
* Evaluating the data only when an answer is specifically requested.
* All the transformations on a dataset are set up as a **DAG**. Spark keeps the record of the series of the transformations requested by user. It groups the transformation in an efficient way when an Action is requested.
* Action : Request a result. Example: the first 10 rows, a sum, a count 
###### Resilient
* Can be reconstructed even if a node crashes
* Every RDD keeps track of where it came from. Every transformations leds to the current RDD and are tracking by Spark as metadata. **This is called RDDs lineage**.
* Lineage also allows lazy instantiation or lazy materilization of RDDs. 

# RDDs, DataFrames, DataSets
### DataFrame
* DataFrame, represents data in tabular format. Using with Python. Very similar RDBMS.
* Every row in a DataFrame represents one record or one representation.
* Every column represent 1 variable ( a list or vector)
* Where does DataFrame come from? ![alt text](http://url/to/img.png)
* **Starting Spark 2.0, APIs for DataSets and DataFrames have merged.**
### Comparisions
![alt text](http://url/to/img.png)
![alt text](http://url/to/img.png)
