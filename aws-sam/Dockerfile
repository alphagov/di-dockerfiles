FROM python:3.10-alpine3.15

ENV AWSCLI_VERSION "2.4.15"
ENV PACKAGES "groff jq gettext"

RUN apk add --no-cache --virtual builddeps gcc musl-dev \
   && pip --no-cache-dir install aws-sam-cli awscli==$AWSCLI_VERSION \
   && apk add $PACKAGES --no-cache \
   && apk del builddeps
