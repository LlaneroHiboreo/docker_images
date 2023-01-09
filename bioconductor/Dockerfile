FROM r-base

RUN apt-get update
RUN apt-get install -y libcurl4 libcurl4-openssl-dev libxml2-dev procps curl unzip  

RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
RUN unzip awscliv2.zip
RUN  ./aws/install

RUN Rscript -e 'if (!requireNamespace("BiocManager", quietly = F)) install.packages("BiocManager") '
RUN Rscript -e 'BiocManager::install(c("dada2","decontam"),update=TRUE, ask=FALSE)'

CMD ["/bin/bash"]
