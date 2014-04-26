FROM ubuntu:13.10
MAINTAINER "Martin Honermeyer" <maze@strahlungsfrei.de>

RUN apt-get -y install wget
RUN echo 'deb http://www.arangodb.org/repositories/arangodb2/xUbuntu_13.10/ /' >> /etc/apt/sources.list.d/arangodb.list && \
    wget http://www.arangodb.org/repositories/arangodb2/xUbuntu_13.10/Release.key && \
    apt-key add - < Release.key
RUN apt-get update && apt-get -y install arangodb=2.0.6

ADD initialize_and_run /

CMD /initialize_and_run
EXPOSE 8529
VOLUME /var/lib/arangodb
