FROM debian:jessie

ENV LANG C.UTF-8
ENV JAVA_VERSION 8u111
ENV CA_CERTIFICATES_JAVA_VERSION 20140324

RUN apt-get update -q && apt-get install -y wget curl \
  && apt-get -q clean -y && rm -rf /var/lib/apt/lists/* && rm -f /var/cache/apt/*.bin
  
# Install Oracle JDK 8u11
RUN mkdir -p /usr/lib/jvm/ && cd /tmp && \
    curl -L -O -H "Cookie: oraclelicense=accept-securebackup-cookie" -k "http://download.oracle.com/otn-pub/java/jdk/8u111-b14/jdk-8u111-linux-x64.tar.gz" && \
    tar xf jdk-8u111-linux-x64.tar.gz -C /usr/lib/jvm/ && rm /tmp/jdk-8u111-linux-x64.tar.gz

ENV JAVA_HOME /usr/lib/jvm/jdk1.8.0_111
ENV CLASSPATH .:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar 
ENV PATH $PATH:$JAVA_HOME/bin
