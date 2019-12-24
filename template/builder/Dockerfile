ARG PREFIX=ruckc
FROM $PREFIX-template-base

RUN yum install git autoconf automake gcc gcc-c++ libtool file diffutils make -y && \
    rm -rf /var/cache/dnf/*
