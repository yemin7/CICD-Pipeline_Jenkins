FROM centos:centos7
COPY daemonize.repo /etc/yum.repo.d/
RUN yum install java-11-openjdk wget ca-certificates epel-release daemonize -y && update-ca-trust
RUN wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo && rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
RUN yum upgrade -y && yum install jenkins -y && yum clean all && rm -rf /var/cache/yum && mkdir /var/jenkins_home
RUN ln -svT "$(dirname $(dirname "$(readlink -f $(whereis java | awk '{print $2}'))"))" /docker-java-home
ENV JAVA_HOME=/docker-java-home
ENV JENKINS_HOME=/var/lib/jenkins
ENV JENKINS_SLAVE_AGENT_PORT=50000
VOLUME /var/lib/jenkins
EXPOSE 8080/tcp
EXPOSE 50000/tcp
USER jenkins
ENTRYPOINT ["java", "-jar", "/usr/lib/jenkins/jenkins.war"]
