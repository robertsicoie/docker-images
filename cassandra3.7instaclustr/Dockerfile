FROM ubuntu:16.04

RUN apt-get update \
	&& apt-get install -y software-properties-common

RUN add-apt-repository ppa:openjdk-r/ppa
RUN apt-get update \
	&& apt-get install -y git ant openjdk-8-jdk

#RUN useradd -ms /bin/bash cassandra
#RUN usermod -aG sudo cassandra

ENV JAVA_HOME /usr/lib/jvm/java-8-openjdk-amd64/
RUN export JAVA_HOME
ENV PATH=$PATH:$JAVA_HOME

#USER cassandra

#WORKDIR /home/cassandra

RUN git clone https://github.com/instaclustr/cassandra.git

RUN cd cassandra && ant build

RUN ./cassandra/bin/cassandra -R

