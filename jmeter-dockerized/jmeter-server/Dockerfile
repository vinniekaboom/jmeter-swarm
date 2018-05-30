FROM vinniekaboom/jmeter-base

LABEL Description="jmeter-server"

EXPOSE 7000 60000

ENTRYPOINT jmeter-server -Jclient.rmi.localport=7000 -Jserver.rmi.localport=60000 -Jserver.rmi.ssl.disable=true:wq!
