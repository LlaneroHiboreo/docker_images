FROM ubuntu:latest

FROM ubuntu

ENV PATH=/root/bin:$PATH

ENV TZ="Europe/Paris"

RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

RUN  apt-get update 
RUN DEBIAN_FRONTEND="noninteractive" apt-get -y install tzdata

RUN  apt-get install -y wget libfindbin-libs-perl perl-base curl unzip openjdk-11-jre unzip gzip libidn11 libgssapi-krb5-2 libbz2-dev libz-dev make gcc libncurses-dev liblzma-dev tzdata  curl  \
  && rm -rf /var/lib/apt/lists/*

RUN mkdir -p /root/bin

RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
RUN unzip awscliv2.zip
RUN  ./aws/install

WORKDIR /usr/local
RUN set -eux; \
       wget -O muscle.tar.gz https://drive5.com/muscle/downloads3.8.31/muscle3.8.31_i86linux64.tar.gz \
    && tar xzvf muscle.tar.gz\
    && rm -f muscle.tar.gz \
    && cp muscle* /root/bin/ \
    && cd /root/bin/ \
    && ln -s muscle* muscle
    

    

