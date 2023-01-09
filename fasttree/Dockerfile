FROM ubuntu

ENV PATH=/root/bin:$PATH

ENV TZ="Europe/Paris"

RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

RUN  apt-get update \
  && apt-get install -y wget gzip libidn11 libgssapi-krb5-2 libbz2-dev libz-dev make unzip gcc libncurses-dev liblzma-dev procps curl  \
  && rm -rf /var/lib/apt/lists/*

RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
RUN unzip awscliv2.zip
RUN  ./aws/install

RUN mkdir -p /root/bin

RUN wget -O /root/bin/FastTree -q http://www.microbesonline.org/fasttree/FastTree && \
chmod +x  /root/bin/FastTree
RUN ln -s /root/bin/FastTree /root/bin/fasttree
