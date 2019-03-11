FROM jenkins/jenkins:lts
USER root
COPY ./settings.xml /etc/
RUN apt-get update \
    && apt-get install -y python-pip \
    && pip install paramiko PyYAML Jinja2 httplib2 six \
    && pip install requests \
    && pip install ansible \
    && apt-get install -y maven \
    && mv /etc/settings.xml /etc/maven/ \
    && mkdir -p /data/repositor \
    && cd /data && wget http://nodejs.org/dist/v10.15.1/node-v10.15.1-linux-x64.tar.xz && tar -xvJf node-v10.15.1-linux-x64.tar.xz && rm node-v10.15.1-linux-x64.tar.xz \
    && ln -s /data/node-v10.15.1-linux-x64/bin/node /usr/bin/node \
    && ln -s /data/node-v10.15.1-linux-x64/bin/npm /usr/bin/npm
USER jenkins
