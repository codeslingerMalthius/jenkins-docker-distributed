FROM jenkins:2.0-alpine
MAINTAINER kmilner@seven10storage.com

USER root
RUN apk add --update perl git &&\
    echo "jenkins ALL=NOPASSWD: ALL" >> /etc/sudoers

COPY bin/setup-docker-and-start-jenkins.sh /usr/local/bin/setup-docker-and-start-jenkins.sh

USER jenkins
COPY plugins.txt /usr/share/jenkins/plugins.txt
RUN /usr/local/bin/plugins.sh /usr/share/jenkins/plugins.txt
USER root
CMD ["/usr/local/bin/setup-docker-and-start-jenkins.sh"]