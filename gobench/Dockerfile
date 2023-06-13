FROM ubuntu:focal
LABEL nginx=server
ARG DEBIAN_FRONTEND=noninteractive
RUN apt-get update -y && apt-get install -y \
    net-tools \
    sshpass \
    gcc \
    wget
RUN wget https://go.dev/dl/go1.17.linux-amd64.tar.gz && \
    tar -C  /usr/local -xzf go1.17.linux-amd64.tar.gz
ENV GOPATH="/go"
ENV PATH=$PATH:/usr/local/go/bin:$GOPATH/bin
RUN go get github.com/cmpxchg16/gobench
RUN mv go /tmp && cp -r /tmp/go/bin/gobench /usr/bin
