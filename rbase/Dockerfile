FROM r-base

#ENV PATH=/root/bin:$PATH

RUN apt-get update && apt-get install -y procps curl unzip 

RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
RUN unzip awscliv2.zip
RUN  ./aws/install


RUN R -e "install.packages(c('ggplot2', 'data.table', 'foreach', 'doParallel', 'dplyr'), repos = c('https://www.freestatistics.org/cran/','https://lib.ugent.be/CRAN/','https://pbil.univ-lyon1.fr/CRAN/', 'https://CRAN.R-project.org/package=data.table'))"

CMD ["/bin/bash"]
