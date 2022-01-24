FROM python:3.10-alpine3.15

RUN apk add --no-cache --virtual builddeps gcc musl-dev && \
   pip --no-cache-dir install aws-sam-cli awscli && \
   apk del builddeps

RUN  apk update \
  && apk upgrade \
  && apk add --update openjdk11 tzdata curl unzip bash \
  && rm -rf /var/cache/apk/*

#install Gradle
RUN wget -q https://services.gradle.org/distributions/gradle-7.3.3-bin.zip \
    && unzip gradle-7.3.3-bin.zip -d /opt \
    && rm gradle-7.3.3-bin.zip

# Set Gradle in the environment variables
ENV GRADLE_HOME /opt/gradle-7.3.3
ENV PATH $PATH:/opt/gradle-7.3.3/bin

RUN	adduser -s /bin/bash samcli \
	--disabled-password \
	&& echo 'samcli ALL=(ALL) NOPASSWD:ALL' >>/etc/sudoers

USER samcli

WORKDIR /home/samcli
