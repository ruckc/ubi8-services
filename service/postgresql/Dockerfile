ARG PREFIX=ruckc
FROM $PREFIX-template-service

RUN yum install https://download.postgresql.org/pub/repos/yum/reporpms/EL-8-x86_64/pgdg-redhat-repo-latest.noarch.rpm -y && \
    yum install postgresql12-server postgresql12-contrib -y && \
    rm -rf /var/cache/dnf/*

COPY dinit.d/* /etc/dinit.d/
COPY pginit /usr/local/bin/pginit

# to validate /etc/dinit.d scripts
RUN /sbin/dinitcheck && \
    chmod 0555 /usr/local/bin/pginit

VOLUME /var/lib/pgsql/12/data

EXPOSE 5432/tcp
