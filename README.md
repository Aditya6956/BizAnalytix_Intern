# BizAnalytix_Intern

INSTALLATION:

Firstly, we need to install Java in our local system, any version above Java 8 is acceptable.

ENTER sudo apt install openjdk-8-jdk in the terminal to install Java

Now, we need to add the JDK path to the environment.

Type nano /etc/environment into your terminal and enter below:

JAVA_HOME="usr/lib/jvm/java-11-openjdk-amd64"

Hit ctrl + s to save and ctrl + x to exit. Once, in terminal type source /etc/environment for Bash to re-read your /etc/environment file.

Now, we Download & install Spark.
Goto Link https://spark.apache.org/downloads.html and select "DOWNLOAD spark-3.3.0-bin-hadoop3.tgz" and install tgz file, extract it to the home folder by 
entering sudo tar -zxvf spark-3.3.0-bin-hadoop3.tgz

Type sudo nano ~/.bashrc in your terminal.
— Enter the environment paths at the end of your .bashrc file below:

source /etc/environment

export SPARK_HOME=/home/aditya/spark-3.3.0-bin-hadoop3

export PATH=$PATH:$SPARK_HOME/bin

export PYSPARK_PYTHON=/usr/local/bin/python3.7

export PYSPARK_DRIVER_PYTHON=/usr/local/bin/python3.7

#when running spark locally, it uses 2 cores, hence local[2]

export PYSPARK_SUBMIT_ARGS="--master local[2] pyspark-shell"

export PYTHONPATH=$SPARK_HOME/python:$PYTHONPATH

export PATH=$PATH:$JAVA_HOME/jre/bin

MAKE SURE TO CHANGE THE PATH OF SPARK HOME ACCORDING TO YOUR SYSTEM.

Hit ctrl + s to save your .bashrc file.
Hit ctrl + x to exit your .bashrc file and go back to your terminal.
Type source ~/.bashrc so Bash can re-read your .bashrc file.

Close the terminal and open a new one..
Type pyspark in the terminal and python shell opens up.

EXECUTION:

In the terminal, type pip install delta-spark.

Open the Jupyter notebook file from the repository and change the path of the dataset and the delta table according to your path and hit the run cell button

A folder will be created in the diretory named "people1" which contains Parquet and CRC files which represent delat tables.
