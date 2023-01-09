FROM ubuntu

ENV PATH=/root/bin:$PATH

ENV TZ="Europe/Paris"

RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone


RUN  apt-get update \
  && apt-get install -y wget gzip python3-pip  libgssapi-krb5-2 libbz2-dev curl unzip libz-dev make gcc libncurses-dev liblzma-dev \
  && rm -rf /var/lib/apt/lists/*

RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
RUN unzip awscliv2.zip
RUN  ./aws/install

RUN mkdir -p /root/bin

RUN pip3 install biom-format
