# FROM ubuntu:focal
# LABEL gobench=clientt
# ARG DEBIAN_FRONTEND=noninteractive
# RUN apt-get update -y && apt-get install -y \
#     net-tools \
#     sshpass \
#     gcc \
#     wget
# RUN wget https://go.dev/dl/go1.17.linux-amd64.tar.gz && \
#     tar -C  /usr/local -xzf go1.17.linux-amd64.tar.gz
# RUN rm -rf go1.17.linux-amd64.tar.gz
# ENV GOPATH="/go"
# ENV PATH=$PATH:/usr/local/go/bin:$GOPATH/bin
# RUN go get github.com/cmpxchg16/gobench
# RUN mv ./go/bin/gobench /usr/bin && rm -rf ./go
FROM ubuntu:focal as builder
LABEL gobench=clienttt
ARG DEBIAN_FRONTEND=noninteractive
RUN apt-get update -y && apt-get install -y \
    net-tools \
    sshpass \
    gcc \
    wget
RUN wget https://go.dev/dl/go1.17.linux-amd64.tar.gz && \
    tar -C  /usr/local -xzf go1.17.linux-amd64.tar.gz
RUN rm -rf go1.17.linux-amd64.tar.gz
ENV GOPATH="/go"
ENV PATH=$PATH:/usr/local/go/bin:$GOPATH/bin
RUN go get github.com/cmpxchg16/gobench
RUN mv ./go/bin/gobench /usr/bin && rm -rf ./go

FROM ubuntu:focal as runner
COPY --from=builder /usr/bin/gobench /usr/bin/gobench
