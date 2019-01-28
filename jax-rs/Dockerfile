# https://www.theserverside.com/video/Step-by-step-RESTful-web-service-example-in-Java-using-Eclipse
FROM sgswc/eclipse

#RUN apt-get update && apt-get install -y \
#	&& true

RUN test -e /opt/java || mkdir /opt/java

#RUN wget http://www.java2s.com/Code/JarDownload/javax.ws/javax.ws.rs.jar.zip -O /root/rs.zip
#RUN unzip /root/rs.zip -d /opt/java

RUN wget -q http://repo1.maven.org/maven2/org/glassfish/jersey/bundles/jaxrs-ri/2.27/jaxrs-ri-2.27.zip -O /root/jaxrs-ri-2.27.zip
RUN unzip /root/jaxrs-ri-2.27.zip -d /opt

RUN wget -q http://www-us.apache.org/dist/tomcat/tomcat-9/v9.0.14/bin/apache-tomcat-9.0.14.tar.gz -O /root/tomcat.tar.gz
RUN tar zxf /root/tomcat.tar.gz -C /opt/ && \
	echo "CATALINA_HOME='/opt/tomcat-9.0.14'" >> /etc/environment

#RUN wget https://nchc.dl.sourceforge.net/project/hibernate/hibernate-orm/5.4.0.Final/hibernate-release-5.4.0.Final.zip -O /root/hib.zip
#RUN unzip -o /root/hib.zip -d /opt

RUN wget http://www.java2s.com/Code/JarDownload/gson/gson-2.2.2.jar.zip -O /root/gson.jar
RUN unzip -o /root/gson.jar -d /opt/java/

EXPOSE 8080
