FROM jenkinsci/jenkins:2.36

#COPY manage_plugins.sh /usr/share/jenkins/ref/
RUN /usr/local/bin/install-plugins.sh git maven-plugin matrix-auth workflow-aggregator docker-workflow blueocean credentials-binding

#COPY plugins.txt /plugins.txt
#RUN /usr/local/bin/install-plugins.sh /plugins.txt


ENV JENKINS_USER admin
ENV JENKINS_PASS admin


# Skip initial setup
ENV JAVA_OPTS -Djenkins.install.runSetupWizard=false

COPY executors.groovy /usr/share/jenkins/ref/init.groovy.d/
COPY default-user.groovy /usr/share/jenkins/ref/init.groovy.d/

VOLUME /var/jenkins_home

#CMD ["/usr/share/jenkins/ref/manage_plugins.sh"]