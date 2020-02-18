FROM ubuntu:latest

MAINTAINER Sang-Heon Jeon "ekffu200098@gmail.com"

# Related uftrace : https://github.com/namhyung/uftrace

ENV DEBIAN_FRONTEND=noninteractive
ENV UFTRACE_HOME=/storage/uftrace

RUN apt-get update && apt-get install -y \
        git gcc make ca-certificates

RUN mkdir -p $UFTRACE_HOME
COPY uftrace $UFTRACE_HOME
WORKDIR $UFTRACE_HOME
RUN ./misc/install-deps.sh -y && ./configure
RUN make && make install
