FROM debian:9.3
MAINTAINER Varlog <varlog.err@gmail.com>

ARG THE_USER
ARG THE_GROUP=${THE_USER}
ARG THE_HOME=/home/${THE_USER}

ADD ["assets", "/tmp/assets"]

RUN /bin/bash /tmp/assets/scripts/create-users \
    && /bin/bash /tmp/assets/scripts/install-wget \
    && cp /tmp/assets/scripts/nvm-runner $THE_HOME \
    && chmod +x $THE_HOME/nvm-runner

USER $THE_USER

RUN wget -qO- https://raw.githubusercontent.com/creationix/nvm/v0.33.8/install.sh | bash

USER root

RUN rm -rf /tmp/assets
