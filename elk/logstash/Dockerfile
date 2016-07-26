FROM daocloud.io/library/java:8

# RUN apt-get update
# RUN apt-get install -y wget build-essential \
#  apt-transport-https curl git libssl-dev python rsync

ENV LOGSTASH_VERSION 2.3.4
ENV LOGSTASH_SRC_DIR /opt/
# RUN cd /tmp && \ 
#     wget https://download.elastic.co/logstash/logstash/logstash-${LOGSTASH_VERSION}.tar.gz && \
#     tar -zxvf ./logstash-${LOGSTASH_VERSION}.tar.gz && \
#     mv ./logstash-${LOGSTASH_VERSION} ${LOGSTASH_SRC_DIR} && \
#     rm ./logstash-${LOGSTASH_VERSION}.tar.gz

ADD ./logstash-${LOGSTASH_VERSION}.tar.gz ${LOGSTASH_SRC_DIR}

WORKDIR ${LOGSTASH_SRC_DIR}/logstash-${LOGSTASH_VERSION}
COPY ./logstash.conf ./config/

ENTRYPOINT ["./bin/logstash", "-f", "./config/logstash.conf"]