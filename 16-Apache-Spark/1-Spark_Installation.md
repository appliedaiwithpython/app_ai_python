### install java 17
http://www.oracle.com/technetwork/java/javase/downloads/index.html . SPARK IS ONLY COMPATIBLE WITH JAVA 8, 11, OR 17 at this time. DO NOT INSTALL JAVA 21+.

### install winrar
If necessary, download and install WinRAR so you can extract the .tgz file you downloaded.
http://www.rarlab.com/download.htm

### download and unzip apache spark
Download a pre-built version of Apache Spark 3 from https://spark.apache.org/downloads.html
Extract the Spark archive, and copy its contents into C:\spark after creating that directory.
Open the the c:\spark\conf folder, and make sure “File Name Extensions” is checked in the “view” tab of Windows Explorer. Rename the log4j2.properties.template file to log4j2.properties
Edit this file (using Wordpad or something similar) and change the error level from “info” to “error” for log4j.root Category

### Add the following new USER variables:
SPARK_HOME: c:\spark
PYSPARK_PYTHON: python
edit path env variable: %SPARK_HOME%\bin

### Test it out!
Open up your Start menu and select “Anaconda Prompt” from the Anaconda3 menu.
Enter cd c:\spark and then dir to get a directory listing.
check README.md or CHANGES.txt exist for the lab

conda env -n py3_8
conda activate py3_8
conda install python=3.8

pyspark
rdd = sc.textFile("c:\spark\README.md")
rdd.count()

Enter quit() to exit the spark shell