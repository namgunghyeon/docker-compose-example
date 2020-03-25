FROM haproxy:2.1

WORKDIR /home

RUN apt-get update
RUN apt-get install -y wget vim git make

RUN wget https://dl.google.com/go/go1.12.1.linux-amd64.tar.gz
RUN tar -C /usr/local -xzf go1.12.1.linux-amd64.tar.gz
ENV PATH=$PATH:/usr/local/go/bin

RUN git clone https://github.com/haproxytech/dataplaneapi.git
RUN cd dataplaneapi && make build

RUN mkdir -p /var/lib/haproxy
RUN mkdir -p /run/haproxy/
RUN mkdir -p /var/run

COPY haproxy.cfg /usr/local/etc/haproxy/haproxy.cfg

EXPOSE 5000 5001