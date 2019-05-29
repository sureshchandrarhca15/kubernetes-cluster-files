FROM docker.io/tomcat

MAINTAINER "sureshchandra.rhca@gmail.com"
 
ENV CATALINA_HOME /usr/local/tomcat
ENV PATH $CATALINA_HOME/bin:$PATH

#Install MySQL Connector for Tomcat

COPY ./jars/mysql-connector-java-5.1.40.jar $CATALINA_HOME/lib/

#Copy Tomcat Config Files
COPY ./conf/*.xml $CATALINA_HOME/conf/

COPY ./manager-context/manager-context.xml $CATALINA_HOME/webapps/manager/META-INF/

COPY ./host-manager-context/host-manager-context.xml $CATALINA_HOME/webapps/host-manager/META-INF/

#Copy Applications to webapps Directory 
ADD ./apps/student.war  $CATALINA_HOME/webapps/

RUN useradd application && chown -R application:application $CATALINA_HOME

USER application
