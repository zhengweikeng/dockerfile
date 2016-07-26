FROM daocloud.io/library/java:8

# RUN apt-get update
# RUN apt-get install -y wget build-essential \
#  apt-transport-https curl git libssl-dev python rsync

ENV ES_VERSION 2.3.4
ENV ES_SRC_DIR /opt/
# RUN cd /tmp && \ 
#     wget https://download.elastic.co/elasticsearch/release/org/elasticsearch/distribution/tar/elasticsearch/2.3.4/elasticsearch-${ES_VERSION}.tar.gz && \
#     tar -zxvf ./elasticsearch-${ES_VERSION}.tar.gz && \
#     mv ./elasticsearch-${ES_VERSION} ${ES_SRC_DIR} && \
#     rm ./elasticsearch-${ES_VERSION}.tar.gz

ADD ./elasticsearch-2.3.4.tar.gz ${ES_SRC_DIR}

WORKDIR ${ES_SRC_DIR}/elasticsearch-${ES_VERSION}
COPY ./elasticsearch.yml ./config/elasticsearch.yml

ENTRYPOINT ["./bin/elasticsearch", "-Des.insecure.allow.root=true"]