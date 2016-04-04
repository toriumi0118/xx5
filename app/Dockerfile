FROM ubuntu
MAINTAINER bobox <bobox@gmail.com>

# install python
RUN apt-get upgrade
RUN apt-get update
RUN apt-get install -y git apt-transport-https curl gcc make openssl libssl-dev libbz2-dev libreadline-dev
RUN curl -O https://www.python.org/ftp/python/3.5.1/Python-3.5.1.tgz
RUN tar xvzf Python-3.5.1.tgz
WORKDIR ./Python-3.5.1
RUN ./configure
RUN make
RUN make install
WORKDIR /
RUN rm -rf Python-3.5.1*
