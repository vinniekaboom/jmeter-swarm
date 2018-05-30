FROM vinniekaboom/jmeter-base:latest

LABEL MAINTAINER="vinniekaboom@protonmail.com"

LABEL Description="jmeter-server"

EXPOSE 1099 50000

ENTRYPOINT $JMETER_HOME/bin/jmeter-server -Dserver_port=1099 -Dserver.rmi.localport=50000 -Jserver.rmi.ssl.disable=true
