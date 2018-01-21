FROM debian:9.3
MAINTAINER Varlog <varlog.err@gmail.com>

ARG THE_USER
ARG THE_USER_ID
ARG THE_GROUP=${THE_USER}
ARG THE_GROUP_ID
ARG THE_HOME=/home/${THE_USER}

ADD ["assets", "/tmp/assets"]

RUN /bin/bash /tmp/assets/scripts/create-users \
    && apt-get update \
    && apt-get install -y build-essential \
                          python \
                          wget \
    && cp /tmp/assets/scripts/nvm-runner / \
    && chmod +x /nvm-runner \
    && cp /tmp/assets/scripts/node-installer / \
    && chmod +x /node-installer \
    && cp /tmp/assets/scripts/nodeutil-runner / \
    && chmod +x /nodeutil-runner \
    && cp /tmp/assets/scripts/node-runner / \
    && chmod +x /node-runner \
    && apt-get autoclean \
    && apt-get autoremove

USER $THE_USER

RUN wget -qO- https://raw.githubusercontent.com/creationix/nvm/v0.33.8/install.sh | bash

USER root

RUN rm -rf /tmp/assets
