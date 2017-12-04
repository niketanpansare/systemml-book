# Introduction to Machine Learning with Apache SystemML

## Table of Content

Chapter 1. Introduction [[nbviewer](http://nbviewer.jupyter.org/github/niketanpansare/systemml-book/blob/master/Chapter1_Introduction.ipynb)] [[ipynb](https://github.com/niketanpansare/systemml-book/blob/master/Chapter1_Introduction.ipynb)]

Chapter 2: Preliminaries [[nbviewer](http://nbviewer.jupyter.org/github/niketanpansare/systemml-book/blob/master/Chapter2_Preliminaries.ipynb)] [[ipynb](https://github.com/niketanpansare/systemml-book/blob/master/Chapter2_Preliminaries.ipynb)]


## Simple instructions for running the notebooks locally

1. Download and install [Anaconda Python](https://www.continuum.io/downloads).

2. Download and extract [Apache Spark](http://spark.apache.org/downloads.html). Set `SPARK_HOME` environment variable.

3. Install [Apache SystemML](http://systemml.apache.org/install-systemml.html): `pip install systemml`

4. Add following to ~/.ipython/profile_default/startup/00-default-setup.py

	```python
	import os
	import sys
	spark_home = os.environ['SPARK_HOME']
	sys.path.insert(0, os.path.join(spark_home, 'python'))
	sys.path.insert(0, os.path.join(spark_home, 'python', 'lib', 'py4j-0.9-src.zip'))
	execfile(os.path.join(spark_home, 'python', 'pyspark', 'shell.py'))
	```

5. Download and start viewing the book

	```
	git clone https://github.com/niketanpansare/systemml-book.git
	cd systemml-book
	jupyter notebook
	```

## (Advanced) Detailed instructions for running the notebooks locally

### On MacOS/Linux

1. Install Java: The Java version should be > 1.8.

	```
	java -version
	```

Set JAVA_HOME environment variable, 

	```
	export JAVA_HOME="$(/usr/libexec/java_home)"
	```

2. Download Spark from https://spark.apache.org/downloads.html and move to home directory, and extract.

	```
	tar -xzf spark-2.1.0-bin-hadoop2.7.tgz
	```
	
and set environment variables to point to the extracted directory,

	```
	export SPARK_HOME="$HOME/spark-2.1.0-bin-hadoop2.7"
	export HADOOP_HOME=$SPARK_HOME
	export SPARK_LOCAL_IP=127.0.0.1
	```
	
3. Install Python, Jupyter, and other libraries: Download and install Anaconda Python 2.7 from https://www.continuum.io/downloads#macos
(includes jupyter, and pip)

	```
	export PYSPARK_DRIVER_PYTHON=jupyter
	export PYSPARK_DRIVER_PYTHON_OPTS='notebook' pyspark
	```
	
4. Install Apache SystemML

	```
	pip install systemml
	```
	
5. Download and start viewing the book

	```
	git clone https://github.com/niketanpansare/systemml-book.git
	cd systemml-book
	$SPARK_HOME/bin/pyspark --master local[*] --driver-memory 8G
	```
	
### On Windows

1. Install Java: The Java version should be > 1.8.

	```
	java -version
	```
	
Set JAVA_HOME environment variable and include %JAVA_HOME%\bin in the environment variable PATH

	```
	ls "%JAVA_HOME%"
	```
	
2. Download and extract Spark from https://spark.apache.org/downloads.html, 

	```
	tar -xzf spark-2.1.0-bin-hadoop2.7.tgz
	```
	
and set environment variable `SPARK_HOME` to point to the extracted directory.
	
Next step, install winutils:

- Download winutils.exe from http://github.com/steveloughran/winutils/raw/master/hadoop-2.6.0/bin/winutils.exe  
- Place it in c:\winutils\bin
- Set environment variable HADOOP_HOME to point to c:\winutils
- Add c:\winutils\bin to the environment variable PATH.
- Finally, modify permission of hive directory that will be used by spark

	```
	winutils.exe chmod 777 /tmp/hive
	```
	
Finally, check if Spark is correctly installed:

	```
	%SPARK_HOME%\bin\spark-shell
	%SPARK_HOME%\bin\pyspark	
	```
	
3. Install Python, Jupyter, and other libraries: Download and install Anaconda Python 2.7 from https://www.continuum.io/downloads
(includes jupyter, and pip)
	
4. Install Apache SystemML

	```
	pip install systemml
	```
	
5. Download and start viewing the book

	```
	git clone https://github.com/niketanpansare/systemml-book.git
	cd systemml-book
	set PYSPARK_DRIVER_PYTHON=jupyter
	set PYSPARK_DRIVER_PYTHON_OPTS=notebook
	%SPARK_HOME%\bin\pyspark --master local[*] --driver-memory 8G
	```