# 
# Dockerfile for build etcd release v3.5.17
# https://github.com/etcd-io/etcd/releases/tag/v3.5.17
# 

FROM ubuntu:22.04

RUN apt-get update

RUN apt-get install make wget git -y

RUN wget https://go.dev/dl/go1.23.3.linux-amd64.tar.gz -O go.tar.gz \
 && tar -xzvf go.tar.gz -C /usr/local && cd go; mkdir GOPATH && echo 'export GOPATH=/usr/local/go/GOPATH' >> ~/.bashrc && echo 'export PATH=$PATH:$GOPATH:/usr/local/go/bin' >> ~/.bashrc 

RUN cd /usr/local; git clone https://github.com/etcd-io/etcd.git; cd etcd && git checkout v3.5.17 && . ~/.bashrc && make; 

RUN mv /usr/local/etcd/bin/etcd /usr/bin && mv /usr/local/etcd/bin/etcdctl /usr/bin && rm -rf /usr/local/etcd && rm -rf /usr/local/go

EXPOSE 2379 2380

CMD ["/usr/bin/etcd"]
