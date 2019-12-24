FROM ubi8/ubi

RUN yum remove *subscription* -y && \
    yum update -y && \
    rm -rf /var/cache/dnf/*
