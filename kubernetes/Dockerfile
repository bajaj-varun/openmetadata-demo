FROM docker.getcollate.io/openmetadata/server:1.6.3

WORKDIR /opt/openmetadata

COPY ./conf/openmetadata.yaml /opt/openmetadata/conf/
COPY ./conf/openmetadata-env.sh /opt/openmetadata/conf/

RUN mkdir ./logs && source conf/openmetadata-env.sh && /opt/openmetadata/bootstrap/openmetadata-ops.sh migrate

EXPOSE 8585 
EXPOSE 8586

ENTRYPOINT /opt/openmetadata/bin/openmetadata-server-start.sh /opt/openmetadata/conf/openmetadata.yaml