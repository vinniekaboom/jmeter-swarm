FROM vinniekaboom/jmeter_base:latest

LABEL MAINTAINER="vinniekaboom@protonmail.com"

LABEL Description="jmeter-master"

RUN apt-get clean && \
    apt-get update && \
    apt-get -qy install \
    git
    
RUN adduser --system jenkins

RUN mkdir /home/jenkins/.ssh

EXPOSE 60000
