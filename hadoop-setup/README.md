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
1. set java_home in hadoop directory	/usr/local/hadoop/etc/hadoop/hadoop-env.sh			/usr/lib/jvm/java-8-openjdk-amd64
2. format node	/usr/local/hadoop/bin/hadoop namenode -format			
3. start hadoop	/usr/local/hadoop/sbin/start-all.sh			
4. check services are running using jps command	jps			
5. check all node is running	sudo netstat -plten | grep java			
6. create a temp directory	mkdir -p /tmp/gutenberg			
7. copy the contents	http://www.gutenberg.org/cache/epub/20417/pg20417.txt			
8. create the hdfs directory	hdfs dfs -mkdir -p /user/hduser			
9. copy files /tmp to hdfs	hadoop hdfs -copyFromLocal /tmp/gutenberg /user/hduser/gutenberg			
to run the example to to this folder - /usr/local/hadoop/share/hadoop/mapreduce	hadoop jar hadoop*examples*.jar wordcount /user/hduser/gutenberg /user/hduser/gutenberg-output			
10. copy the output 	hadoop hdfs -getmerge /user/hduser/gutenberg-output /tmp/gutenberg-output			


