FROM composer:1.6
MAINTAINER Varlog <varlog.err@gmail.com>

ARG THE_USER
ARG THE_USER_ID
ARG THE_GROUP=${THE_USER}
ARG THE_GROUP_ID
ARG THE_HOME=/home/${THE_USER}
ENV COMPOSER_HOME=${THE_HOME}

ADD ["assets", "/tmp/assets"]

RUN /bin/bash /tmp/assets/scripts/create-users \
    && /bin/bash /tmp/assets/scripts/export-path \
    && mv /tmp/assets/scripts/install-and-run / \
    && chmod 0777 /install-and-run \
    && rm -rf /tmp/assets
