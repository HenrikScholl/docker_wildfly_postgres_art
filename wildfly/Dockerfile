FROM jboss/wildfly:latest
MAINTAINER Sven Guthe <sven_guthe@web.de>

# define the deployments directory as a volume that can be mounted
VOLUME /opt/jboss/wildfly/standalone/deployments

ADD com.ewolff/user-registration-application/0.0.1-SNAPSHOT/user-registration-application-0.0.1-SNAPSHOT.war /opt/jboss/wildfly/standalone/deployments

# Add a management user named 'admin' 
RUN /opt/jboss/wildfly/bin/add-user.sh -u admin -p admin --silent

# expose debug port
EXPOSE 8787

# start WildFly in standalone/debug mode and allow management from host 
CMD ["/opt/jboss/wildfly/bin/standalone.sh", "-c", "standalone.xml", "-b", "0.0.0.0", "-bmanagement", "0.0.0.0" , "--debug"]
