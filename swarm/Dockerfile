FROM ubuntu

ENV PATH=/root/bin:$PATH

ENV TZ="Europe/Paris"

RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

RUN  apt-get update \
  && apt-get install -y wget gzip  libgssapi-krb5-2 curl unzip libbz2-dev libz-dev make gcc libncurses-dev liblzma-dev  \
  && rm -rf /var/lib/apt/lists/*

RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
RUN unzip awscliv2.zip
RUN  ./aws/install

RUN mkdir -p /root/bin
RUN wget -qO - https://github.com/torognes/swarm/releases/download/v3.1.0/swarm-3.1.0-linux-x86_64.tar.gz |  tar xvz -C /tmp/ && \
cd /tmp/swarm-3.1.0-linux-x86_64/bin  && \
cp swarm /root/bin/ 
