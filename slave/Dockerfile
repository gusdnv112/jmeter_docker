FROM docker.io/s390x/ibmjava:8-sdk
MAINTAINER HWPARK_Dalpeng

WORKDIR /usr/local
RUN apt-get update
RUN apt-get install wget

RUN wget https://archive.apache.org/dist/jmeter/binaries/apache-jmeter-5.4.1.tgz
RUN tar -xvzf apache-jmeter-5.4.1.tgz
RUN ln -s apache-jmeter-5.4.1 jmeter
RUN wget https://repo1.maven.org/maven2/kg/apc/jmeter-plugins-manager/1.6/jmeter-plugins-manager-1.6.jar
RUN wget https://repo1.maven.org/maven2/kg/apc/cmdrunner/2.0/cmdrunner-2.0.jar
#RUN java -cp /usr/local/jmeter/lib/ext/plugins-manager.jar org.jmeterplugins.repository.PluginManagerCMDInstaller
#RUN /usr/local/jmeter/bin/PluginsManagerCMD.sh install jpgc-autostop,jpgc-casutg,jpgc-csl,jpgc-dummy,jpgc-ffw,jpgc-filterresults,jpgc-functions,jpgc-json,jpgc-mergeresults,jpgc-prmctl,jpgc-sense,jpgc-tst,jpgc-wsc
EXPOSE 1099
RUN echo server.rmi.ssl.disable=ture >> jmeter.properties

ENTRYPOINT /usr/local/jmeter/bin/jmeter-server -Dserver_port=1099