# Introduction to Machine Learning with Apache SystemML

## Table of Content

Chapter 1. [Introduction](http://nbviewer.jupyter.org/github/niketanpansare/systemml-book/blob/master/Chapter1_Introduction.ipynb)

## Run the notebooks locally

1. Download Anaconda and Spark 

2. Set SPARK_HOME environment variable

3. Add following to ~/.ipython/profile_default/startup/00-default-setup.py

```python
import os
import sys
spark_home = 'C:\\Users\\npansar\\Documents\\Projects\\spark-1.6.1-bin-hadoop2.6'
sys.path.insert(0, os.path.join(spark_home, 'python'))
sys.path.insert(0, os.path.join(spark_home, 'python', 'lib', 'py4j-0.9-src.zip'))
execfile(os.path.join(spark_home, 'python', 'pyspark', 'shell.py'))
```

4. Download and start viewing the book

```bash
git clone https://github.com/niketanpansare/systemml-book.git
cd systemml-book
jupyter notebook
```
