FROM composer:1.6
MAINTAINER Varlog <varlog.err@gmail.com>

ARG THE_USER
ARG THE_GROUP=${THE_USER}
ARG THE_HOME=/home/${THE_USER}
ENV COMPOSER_HOME=${THE_HOME}

ADD ["assets", "/tmp/assets"]

RUN /bin/bash /tmp/assets/scripts/create-users \
    && /bin/bash /tmp/assets/scripts/export-path \
    && rm -rf /tmp/assets
