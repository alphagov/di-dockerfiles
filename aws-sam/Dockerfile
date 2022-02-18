FROM python:3.10-alpine3.15

ENV PACKAGES "jq gettext"

RUN apk add --no-cache --virtual builddeps gcc musl-dev \
   && pip --no-cache-dir install aws-sam-cli awscli \
   && apk add $PACKAGES --no-cache \
   && apk del builddeps
