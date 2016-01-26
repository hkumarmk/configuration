FROM ubuntu:trusty
MAINTAINER edxops 
ENV ANSIBLE_REPO="https://github.com/edx/ansible"
ENV CONFIGURATION_REPO="https://github.com/edx/configuration.git"
ENV CONFIGURATION_VERSION="master"

COPY util/install/apt-keys /keys
RUN apt-key add /keys
ADD util/install/ansible-bootstrap.sh /tmp/ansible-bootstrap.sh
RUN echo 'APT::Get::AllowUnauthenticated "true";' > /etc/apt/apt.conf.d/99auth
RUN chmod +x /tmp/ansible-bootstrap.sh
RUN /tmp/ansible-bootstrap.sh
