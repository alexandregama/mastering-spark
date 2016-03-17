# Mastering Spark

## Spark Mechanics

![Spark Mechanics](http://spark.apache.org/docs/latest/img/cluster-overview.png)

## Running on a cluster in Apache runtime Architecture

#### Basic Concepts

In distributed mode, Spark uses a **master/slave** architecture with one **central coordinator** and many distributed **workers**.

The central coordinator is called **driver**. The driver runs in ints own Java Process and each work runs in its Java Process too.

As noted, Spark is packaged with a built-in cluster manager called the Standalone cluster manager. To manage a cluster, Spark works great with **Apache Mesos** and **Hadoop YARN**.

#### The Driver

Here we have the **main process** running. When the Driver runs, it performs two duties:

- Converting a user program into tasks
- Scheduling tasks on executors

Tasks are the smallest unit of work in Spark. Each executor represents a process capable of running tasks and storing RDD data.

#### The Executor

Spark executors are worker processes responsible for running the individual tasks in a given Spark job. 
Executors has two roles: 
- **First**: They run the tasks that make up the application and return results to the Driver
- **Second**: They provide in-memory storage for RDDs that are cached by user programs

#### Cluster Manager
