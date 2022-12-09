ARG BASE_IMAGE
FROM ${BASE_IMAGE}

LABEL description="Docker container for developing go stuff."

# darwin or linux=
ARG PLATFORM
ARG GO_VERSION


# Config
# ENV GO_VERSION=1.18.4

# Install additional tools
RUN apt-get update && apt-get upgrade -y && \
    apt-get install -y git asciidoctor curl sudo apt-utils build-essential sshpass rsync unzip hugo && \
    rm -rf /var/lib/apt/lists/* 

# Golang
RUN curl -4 -L -k https://golang.org/dl/go${GO_VERSION}.${PLATFORM}.tar.gz -o /tmp/go${GO_VERSION}.tar.gz && \
    tar -xzf /tmp/go${GO_VERSION}.tar.gz -C /tmp && \
    mv /tmp/go /usr/local/sbin/go && \
    rm -rf /tmp/*

ENV PATH="/usr/local/sbin/go/bin:${PATH}"
