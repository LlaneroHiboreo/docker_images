FROM ubuntu:latest

FROM ubuntu

ENV PATH=/root/bin:$PATH
ENV TZ="Europe/Paris"

RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

RUN  apt-get update \
  && apt-get install -y wget openjdk-11-jre gzip  libgssapi-krb5-2 libbz2-dev libz-dev make gcc libncurses-dev liblzma-dev curl unzip  \
  && rm -rf /var/lib/apt/lists/*

RUN mkdir -p /root/bin

RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
RUN unzip awscliv2.zip
RUN  ./aws/install

ENV BBMAP_VERSION 38.94
ENV BBMAP_DIR /usr/local/bbmap

WORKDIR /usr/local
RUN set -eux; \
       wget -O bbmap.tar.gz https://sourceforge.net/projects/bbmap/files/BBMap_${BBMAP_VERSION}.tar.gz/download \
    && tar -zxf bbmap.tar.gz \
    && rm bbmap.tar.gz


RUN cd /usr/local/bbmap/jni \
    && make -f makefile.linux
ENV PATH ${BBMAP_DIR}:${PATH}

