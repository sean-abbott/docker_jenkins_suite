FROM jenkinsci/jenkins:lts

USER jenkins
ADD config/config.xml /var/jenkins_home/config.xml
ADD config/github-plugin-configuration.xml /var/jenkins_home/github-plugin-configuration.xml
ADD config/jenkins.model.JenkinsLocationConfiguration.xml /var/jenkins_home/jenkins.model.JenkinsLocationConfiguration.xml
ADD config/jenkins.CLI.xml /var/jenkins_home/jenkins.CLI.xml
ADD config/plugins.txt /usr/share/jenkins/plugins.txt

RUN /usr/local/bin/plugins.sh /usr/share/jenkins/plugins.txt
