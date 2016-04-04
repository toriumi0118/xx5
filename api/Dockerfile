FROM ubuntu
MAINTAINER bobox <bobox@gmail.com>

# install scala, finagle
RUN apt-get upgrade
RUN apt-get install -y git apt-transport-https curl
RUN echo "deb https://dl.bintray.com/sbt/debian /" | sudo tee -a /etc/apt/sources.list.d/sbt.list
RUN apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 642AC823
RUN apt-get update
RUN apt-get install -y sbt
# RUN git clone https://github.com/twitter/finagle.git
# WORKDIR finagle/doc/src/sphinx/code/quickstart
# RUN ./sbt compile
# ENTRYPOINT ./sbt 'run-main Server'
