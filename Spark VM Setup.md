
Spark VM Setup

Deployment Platform:
--------------------

i. Platform Requirements
•	Operating System: You can use Ubuntu 14.04 or later (other Linux flavors can also be used like CentOS, Red hat, etc.)
•	Spark: Apache Spark 1.6.1 or later


ii. Setup Platform :
--------------------

If you are using Windows / Mac OS you can create a virtual machine and install Ubuntu using VMWare Player, alternatively, you can create a virtual machine and install Ubuntu using Oracle Virtual Box.

 



iii. OS Platform :
-------------------
 
Spark installation on Ubuntu:
-----------------------------
Step 1: 
--------
Before installing Spark, you need to First ensure that java8 is installed:

 1  sudo add-apt-repository ppa:webupd8team/java
 
 2  sudo apt-get update
 
 3  sudo apt-get install oracle-java8-installer
 

Verify that java is correctly installed:
-----------------------------------------

1	    java -version    


If not, install the Java in Ubuntu OS.

Configuring Java Environment : 
-------------------------------

sudo apt-get install oracle-java8-set-default  




Step 2: 
--------

Download Apache Spark:
------------------------

	Go to downloads page

	Choose a Spark release: 2.1.1 (May 02 2017)

	Choose a package type: Pre-built for Hadoop 2.6



Step 3: 
--------

	Open the terminal (Ctrl+Alt+t).

	Change the directory to spark  ~$ cd ~/spark


Step 4: 
---------

Complete the installation process

	Move the downloaded file “spark-2.1.1-bin-hadoop2.7.tgz” to your home (~)

	Compress it

  	 tar -xf spark-2.1.1-bin-hadoop2.6.tgz
     

Create a link to spark installation:
--------------------------------------

1	    sudo ln -s ~/spark-2.1.1-bin-hadoop2.7 /usr/local/spark


Edit bashrc using this command line:
-------------------------------------

1   cd

2   sudo gedit .bashrc


Add the below lines in bashrc
-------------------------------

1   # - SPARK ENVIRONMENT VARIABLES START -#

2   export SPARK_HOME=/usr/local/spark (# PATH)

3   export PATH=$SPARK_HOME/bin:$PATH

4   # — SPARK ENVIRONMENT VARIABLES END — #


Note: 
------


If you are getting error to include the above statement in bashrc. Please change the permission mode in terminal.


 $ chmod 755 ~/.bashrc


Environment variables to reflect on the current shell, source the file. 


~$ source ~/.bashrc


Execute bashrc: 

~/.bashrc
 
Check the changes applied properly


~$ echo $SPARK_HOME 

~$ which spark-shell


Step 5: Test the installation
------------------------------


•	Execute this command line:


1	    spark-shell


To make sure the spark-shell started properly without errors, execute below commands 


~$ print(“sc”) 
~$ print(“spark”)
