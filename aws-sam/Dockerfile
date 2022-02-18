FROM python:3.10-alpine3.15

ENV AWSCLI_VERSION "2.0.2"
ENV PACKAGES "groff jq gettext"

RUN apk add --no-cache --virtual builddeps gcc musl-dev \
   && pip --no-cache-dir install aws-sam-cli awscliv2==$AWSCLI_VERSION \
   && apk add $PACKAGES --no-cache \
   && apk del builddeps
