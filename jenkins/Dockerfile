FROM jenkinsci/jenkins:lts

ADD config/config.xml /var/jenkins_home/config.xml
ADD config/github-plugin-configuration.xml /var/jenkins_home/github-plugin-configuration.xml
ADD config/plugins.txt /usr/share/jenkins/plugins.txt

RUN /usr/local/bin/install-plugins.sh /usr/share/jenkins/plugins.txt
