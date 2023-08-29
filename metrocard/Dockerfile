FROM voltdb/voltdb-enterprise:latest

ARG volt_uid=1001
ARG volt_gid=1001 

USER 1001:1001

COPY metrocard.tar  /opt/voltdb/

WORKDIR /opt/voltdb/

USER root

RUN tar -xvf metrocard.tar -C /opt/voltdb && \
    chown -R 1001:1001 /opt/voltdb/metrocard
USER 1001:1001

WORKDIR /opt/voltdb/metrocard

CMD exec /bin/sh -c "trap : TERM INT; sleep 9999999999d & wait"
