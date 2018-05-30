FROM vinniekaboom/jmeter-base:latest

LABEL MAINTAINER="vinniekaboom@protonmail.com"

LABEL Description="jmeter-server"

EXPOSE 7000 60000

ENTRYPOINT jmeter-server -Jclient.rmi.localport=7000 -Jserver.rmi.localport=60000 -Jserver.rmi.ssl.disable=true
