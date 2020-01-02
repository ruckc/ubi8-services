ARG PREFIX=ruckc
FROM $PREFIX-template-builder AS build

#ARG DINIT_VERSION=0.8.0

RUN cd /tmp && \
    #curl -L https://github.com/davmac314/dinit/archive/v${DINIT_VERSION}.tar.gz -o dinit.tar.gz && \
    #tar -zxvf dinit.tar.gz && \
    git clone https://github.com/davmac314/dinit.git dinit && \
    cd dinit && \
    make BUILD_SHUTDOWN=no && \
    make install 

FROM $PREFIX-template-base

COPY --from=build /sbin/dinit* /sbin
RUN mkdir /etc/dinit.d
ENTRYPOINT /sbin/dinit
