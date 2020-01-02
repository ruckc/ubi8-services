FROM registry.redhat.io/ubi8/ubi

RUN yum remove *subscription* -y && \
    yum update -y -v && \
    rm -rf /var/cache/dnf/*
