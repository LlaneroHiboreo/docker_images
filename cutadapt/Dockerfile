FROM ubuntu

ENV TZ="Europe/Paris"

RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

RUN apt-get -qq update && apt-get -y upgrade && \
	apt-get install -y python3-pip python3-dev build-essential unzip curl

RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
RUN unzip awscliv2.zip
RUN  ./aws/install

RUN pip3 install  pip && \
	pip3 install virtualenv

RUN pip3 install --user --upgrade cutadapt && \
	ln -s /root/.local/bin/cutadapt /usr/bin/

#ENTRYPOINT ["cutadapt"]