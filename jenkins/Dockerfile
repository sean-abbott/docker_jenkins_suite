FROM jenkinsci/jenkins:lts

# These adds can be templates in, such as by https://github.com/sean-abbott/dc_jenkins
USER root
ADD config/config.xml /var/jenkins_home/config.xml
ADD config/github-plugin-configuration.xml /var/jenkins_home/github-plugin-configuration.xml
ADD config/jenkins.model.JenkinsLocationConfiguration.xml /var/jenkins_home/jenkins.model.JenkinsLocationConfiguration.xml
ADD config/jenkins.CLI.xml /var/jenkins_home/jenkins.CLI.xml
ADD config/hudson.plugins.git.GitSCM.xml /var/jenkins_home/hudson.plugins.git.GitSCM.xml
ADD config/plugins.txt /usr/share/jenkins/plugins.txt

RUN mkdir /var/jenkins_home/.ssh/
COPY config/id_rsa /var/jenkins_home/.ssh/id_rsa
COPY config/id_rsa.pub /var/jenkins_home/.ssh/id_rsa.pub
RUN chown -R jenkins:jenkins /var/jenkins_home && \
    chown -R jenkins:jenkins /var/jenkins_home/.ssh/ && \
    chown jenkins:jenkins /var/jenkins_home/config.xml

USER jenkins
RUN /usr/local/bin/plugins.sh /usr/share/jenkins/plugins.txt
