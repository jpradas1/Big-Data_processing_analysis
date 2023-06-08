# Big Data Processing & Analysis

This repository contains the topics that were taught in the coursera course [Big Data: procesamiento y análisis](https://www.coursera.org/learn/big-data-procesamiento-analisis). This course focus on machine learning methods applied with Spark, moreover it implement Hadoop as the tool to create, store and manage database. The course is formed by 4 modules. Before starting, let's see the setup to reproduce each jupyter script in this project.

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
## Topics
The structure of the course is over four week. In the first week the course focus on the introduction to handle Spark from Jupyter Notebooks, here we use libraries and modules as SQLContext and SparkContext to reach the database store in hadoop services and performe queries on this database. The following modules o weeks are related to machine learning algorithms applied with Spark. Here we find how to implement simple models as Linear and Logistics Regression, or implemnent more complex models as Regression and Decision Trees and Neural Networks.

Finally, the last [Assignment](https://github.com/jpradas1/Big-Data_processing_analysis/blob/main/Week_4/Final_Assignment.ipynb) analyzes the delay of airplanes on Augost 2017.
