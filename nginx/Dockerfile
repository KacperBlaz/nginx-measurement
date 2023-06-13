FROM ubuntu:focal
LABEL gobench=client
RUN apt update -y && apt install nginx -y \
    net-tools -y \
    ethtool -y
EXPOSE 80
COPY run.sh /tmp
ENTRYPOINT ["/tmp/run.sh"]