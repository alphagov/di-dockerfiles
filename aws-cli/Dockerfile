FROM amazon/aws-cli:2.4.19

ENV PACKAGES "jq gettext"

RUN yum update -y \
    && yum install -y $PACKAGES \
    && yum -y clean all \
    && rm -rf /var/cache
