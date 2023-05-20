# Big Data Processing & Analysis

This repository contains the topics that were taught in the coursera course [Big Data: procesamiento y análisis](https://www.coursera.org/learn/big-data-procesamiento-analisis). This course focus on machine learning methos applied with Spark, moreover it implement Hadoop as the tool to create the database. The course consist in 4 modules. Before starting, let's see the setup to reproduce each jupyter script in this project.

## Virtual Machine Cloudera
The use has been made of a virtual machine of cloudera service. This machine can be reached [here(1)](https://public.pic.es/s/PzlNo48KSQL0qDY/download) or [here(2)](https://downloads.cloudera.com/demo_vm/virtualbox/cloudera-quickstart-vm-5.12.0-0-virtualbox.zip). Then once you have installed the environment on [VirtualBox](https://www.virtualbox.org/), it is needed to install conda and Spark tools. Run this on the Cloudera shell:
```
wget https://raw.githubusercontent.com/pic-es/BigDataMOOC/master/scripts/setup_pyspark.sh
. setup_pyspark.sh
```
This is going to install the conda package managment, with Spark by defaulf. So to start a jupyter notebook, run:
```
pyspark
```
### Databricks Config and Dataset
The require dataset is located in the folder **dataset**, so just perform a suitable unzip for each file, i.e.:
```
tar -xzf On_Time_On_Time_Performance_2016_12.tar.gz
unzip Final-Assignment.zip
```
To set Databrick, SparkContext and SQLContext for jupyter notebooks, run this in the path */home/cloudera/*:
```
unzip jar-packages.zip
conda install seaborn
pyspark --jars /home/cloudera/spark-csv_2.10-1.5.0.jar,/home/cloudera/commons-csv-1.4.jar
```
The last line lunchs the jupyter noteboook.

### Hadoop Setting
Once you have unzip the datasets, these have to be putted into Hadoop. For that run:
```
hdfs dfs -put (...)/On_Time_On_Time_Performance_2016_12.csv /user/cloudera/
hdfs dfs -put (...)/On_Time_On_Time_Performance_2017_8.csv /user/cloudera/
```
