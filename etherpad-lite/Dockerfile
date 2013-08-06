FROM ubuntu

RUN apt-get install -y python-software-properties && add-apt-repository ppa:chris-lea/node.js
RUN sed -i "s/main/main universe/" /etc/apt/sources.list && apt-get update && apt-get -y install gzip git-core curl python libssl-dev pkg-config build-essential nodejs

RUN git clone git://github.com/ether/etherpad-lite.git
RUN cd etherpad-lite && bin/installDeps.sh

CMD cd etherpad-lite && bin/run.sh
