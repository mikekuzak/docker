FROM local/centos-base
MAINTAINER "mkuzak" <michal.kuzak@gmail.com>
ENV JAVA_VERSION 8u121
ENV BUILD_VERSION b13
ENV KEY e9e7ea248e2c4826b92b3f075a80e441

# Install Java
RUN yum -y install wget
RUN wget --no-cookies --no-check-certificate --header "Cookie: oraclelicense=accept-securebackup-cookie" "http://download.oracle.com/otn-pub/java/jdk/$JAVA_VERSION-$BUILD_VERSION/$KEY/jdk-$JAVA_VERSION-linux-x64.rpm" -O /tmp/jdk-8-linux-x64.rpm

RUN yum -y install /tmp/jdk-8-linux-x64.rpm

RUN alternatives --install /usr/bin/java jar /usr/java/latest/bin/java 200000
RUN alternatives --install /usr/bin/javaws javaws /usr/java/latest/bin/javaws 200000
RUN alternatives --install /usr/bin/javac javac /usr/java/latest/bin/javac 200000

ENV JAVA_HOME /usr/java/latest
RUN rm -f /tmp/jdk-8-linux-x64.rpm

