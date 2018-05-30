FROM ubuntu:latest

LABEL MAINTAINER="vinniekaboom@protonmail.com"

LABEL Description="jmeter-base"

# JMeter version
ARG JMETER_VERSION=4.0

# Install utilities
RUN apt-get clean && \
    apt-get update && \
    apt-get -qy install \
    wget \
    default-jre-headless \
    telnet \
    iputils-ping \
    unzip \
    git

# Adding Jenkins user
RUN adduser --system jenkins

RUN groupadd docker

RUN usermod -aG docker jenkins

# Installing jmeter
RUN mkdir /jmeter \
    && cd /jmeter/ \
    && wget https://archive.apache.org/dist/jmeter/binaries/apache-jmeter-$JMETER_VERSION.tgz \
    && tar -xzf apache-jmeter-$JMETER_VERSION.tgz \
    && rm apache-jmeter-$JMETER_VERSION.tgz \
    && mkdir /jmeter-plugins \
    && cd /jmeter-plugins/ \
    && wget https://jmeter-plugins.org/downloads/file/JMeterPlugins-ExtrasLibs-1.4.0.zip \
    && unzip -o JMeterPlugins-ExtrasLibs-1.4.0.zip -d /jmeter/apache-jmeter-$JMETER_VERSION/ \
    && rm JMeterPlugins-ExtrasLibs-1.4.0.zip

# Set JMeter Home
ENV JMETER_HOME /jmeter/apache-jmeter-$JMETER_VERSION/

# Add JMeter to the Path
ENV PATH $JMETER_HOME/bin:$PATH
