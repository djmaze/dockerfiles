FROM ubuntu:14.04
MAINTAINER "Martin Honermeyer" <maze@strahlungsfrei.de>

RUN apt-get -y install wget apt-transport-https
RUN echo 'deb http://www.arangodb.org/repositories/arangodb2/xUbuntu_14.04/ /' >> /etc/apt/sources.list.d/arangodb.list && \
    wget http://www.arangodb.org/repositories/arangodb2/xUbuntu_14.04/Release.key && \
    apt-key add - < Release.key
RUN apt-get update && apt-get -y install arangodb=2.0.9

ADD initialize_and_run /

CMD ["/initialize_and_run"]
EXPOSE 8529
VOLUME /var/lib/arangodb
