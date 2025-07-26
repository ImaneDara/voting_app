FROM jenkins/jenkins:lts

USER root

# Installer curl, sudo et Docker
RUN apt-get update && \
    apt-get install -y curl sudo

RUN curl -fsSL https://get.docker.com | sh && \
    usermod -aG docker jenkins

# Installer docker-compose
RUN curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" \
     -o /usr/local/bin/docker-compose && \
    chmod +x /usr/local/bin/docker-compose

USER jenkins

