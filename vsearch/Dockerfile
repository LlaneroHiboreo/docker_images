FROM ubuntu:latest

ENV PATH=/root/bin:$PATH
ENV TZ="Europe/Paris"

RUN apt-get  update
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

RUN  apt-get update \
  && apt-get install -y wget gzip  libgssapi-krb5-2 unzip libbz2-dev libz-dev make gcc libncurses-dev liblzma-dev curl unzip  \
  && rm -rf /var/lib/apt/lists/*

RUN mkdir -p /root/bin

RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
RUN unzip awscliv2.zip
RUN  ./aws/install

RUN wget -qO - https://github.com/torognes/vsearch/releases/download/v2.21.0/vsearch-2.21.0-linux-x86_64.tar.gz | tar xvz -C /tmp/ && \
cd /tmp/vsearch-2.21.0-linux-x86_64/bin  && \
cp vsearch /root/bin/ && \
rm -rf /tmp/vsearch-2.21.0-linux-x86_64
