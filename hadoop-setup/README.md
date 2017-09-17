# Ansible Role: Java

[![Build Status](https://travis-ci.org/geerlingguy/ansible-role-java.svg?branch=master)](https://travis-ci.org/geerlingguy/ansible-role-java)

Installs Java for RedHat/CentOS and Debian/Ubuntu linux servers.

## Requirements

This is a good article to run a multi-node hadoop cluster and widely followed.
http://www.michael-noll.com/tutorials/running-hadoop-on-ubuntu-linux-single-node-cluster/

Setting up multi node cluster is time consuming and repetitive.
This ansible script will replicate the same process and setup the multi node cluster using Vagrant.

## How to run the playbook

1. Clone this repository
2. vagrant up


## Setup
1. change to user - sudo su hduser
2. Source the .bashrc file
3. set java_home in hadoop directory	/usr/local/hadoop/etc/hadoop/hadoop-env.sh			/usr/lib/jvm/java-8-openjdk-amd64
4. format node	/usr/local/hadoop/bin/hadoop namenode -format			
5. start hadoop	/usr/local/hadoop/sbin/start-all.sh			
6. check services are running using jps command	jps			
7. check all node is running	sudo netstat -plten | grep java			
8. create a temp directory	mkdir -p /tmp/gutenberg			
9. copy the contents	http://www.gutenberg.org/cache/epub/20417/pg20417.txt			
10. create the hdfs directory	hdfs dfs -mkdir -p /user/hduser			
11. copy files /tmp to hdfs	- hadoop(hdfs) dfs -copyFromLocal /tmp/gutenberg /user/hduser/gutenberg			
12. List the files - hadoop(hdfs) dfs -ls /user/hduser
13. to run the example to to this folder - /usr/local/hadoop/share/hadoop/mapreduce	<hadoop jar hadoop(star-*)examples(star-*).jar wordcount /user/hduser/gutenberg /user/hduser/gutenberg-output>			
14. copy the output 	hadoop hdfs -getmerge /user/hduser/gutenberg-output /tmp/gutenberg-output			


