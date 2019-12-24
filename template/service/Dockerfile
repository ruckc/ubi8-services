ARG PREFIX=ruckc
FROM $PREFIX-template-builder AS build

ARG DINIT_VERSION=0.8.0

RUN cd /tmp && \
    curl -L https://github.com/davmac314/dinit/archive/v${DINIT_VERSION}.tar.gz -o dinit.tar.gz && \
    tar -zxvf dinit.tar.gz && \
    cd dinit-${DINIT_VERSION} && \
    make && \
    make install 

FROM $PREFIX-template-base

COPY --from=build /sbin/dinit* /sbin

RUN mkdir /etc/dinit.d
