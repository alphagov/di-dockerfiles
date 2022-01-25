FROM ghcr.io/alphagov/aws-sam:latest

# Install Java
RUN apk update \
  && apk upgrade \
  && apk add --update openjdk11 tzdata curl unzip bash \
  && rm -rf /var/cache/apk/*

# Install Gradle
ENV GRADLE_VERSION=7.3.3
ARG GRADLE_BIN_SHA256=b586e04868a22fd817c8971330fec37e298f3242eb85c374181b12d637f80302

RUN wget -q https://services.gradle.org/distributions/gradle-${GRADLE_VERSION}-bin.zip \
    && echo "${GRADLE_BIN_SHA256} *gradle-${GRADLE_VERSION}-bin.zip" | sha256sum -c - \
    && unzip gradle-${GRADLE_VERSION}-bin.zip -d /opt \
    && rm gradle-${GRADLE_VERSION}-bin.zip

# Set Gradle in the environment variables
ENV GRADLE_HOME /opt/gradle-${GRADLE_VERSION}
ENV PATH $PATH:/opt/gradle-${GRADLE_VERSION}/bin
