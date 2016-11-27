# Introduction to Machine Learning with Apache SystemML

## Table of Content

Chapter 1. Introduction [[nbviewer](http://nbviewer.jupyter.org/github/niketanpansare/systemml-book/blob/master/Chapter1_Introduction.ipynb)] [[ipynb](https://github.com/niketanpansare/systemml-book/blob/master/Chapter1_Introduction.ipynb)]

## Run the notebooks locally

1. Download [Anaconda Python](https://www.continuum.io/downloads) and [Apache Spark](http://spark.apache.org/downloads.html)

2. Set SPARK_HOME environment variable

3. Install [Apache SystemML](https://apache.github.io/incubator-systemml/beginners-guide-python#install-systemml)

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

  ```bash
  git clone https://github.com/niketanpansare/systemml-book.git
  cd systemml-book
  jupyter notebook
  ```
