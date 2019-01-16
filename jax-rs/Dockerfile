FROM sgswc/eclipse

RUN apt-get update && apt-get install -y \
	curl \
	unzip \
	wget \
	&& true

RUN test -e /opt/java || mkdir /opt/java

RUN wget http://www.java2s.com/Code/JarDownload/javax.ws/javax.ws.rs.jar.zip -O /root/rs.zip
RUN unzip /root/rs.zip -d /opt/java

RUN wget http://repo1.maven.org/maven2/org/glassfish/jersey/bundles/jaxrs-ri/2.27/jaxrs-ri-2.27.zip -O /root/jaxrs-ri-2.27.zip
RUN mkdir /tmp/java && unzip /root/jaxrs-ri-2.27.zip -d /tmp/java && \
	mv /tmp/java/jaxrs-ri/*/*.jar /opt/java/. && \
	rm -rf /tmp/java


