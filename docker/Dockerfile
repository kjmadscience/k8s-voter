FROM voltdb/voltdb-enterprise:latest

ARG volt_uid=1001
ARG volt_gid=1001 

USER 1001:1001

COPY voter1.tar  /opt/voltdb/

WORKDIR /opt/voltdb/

USER root

RUN tar -xvf voter1.tar -C /opt/voltdb && \
    chown -R 1001:1001 /opt/voltdb/voter
USER 1001:1001

WORKDIR /opt/voltdb/voter

CMD exec /bin/sh -c "trap : TERM INT; sleep 9999999999d & wait"
