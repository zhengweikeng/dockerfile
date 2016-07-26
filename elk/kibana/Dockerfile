FROM daocloud.io/library/java:8

# RUN apt-get update
# RUN apt-get install -y wget build-essential \
#  apt-transport-https curl git libssl-dev python rsync

ENV KIBANA_VERSION 4.5.3-linux-x64
ENV KIBANA_SRC_DIR /opt
# RUN cd /tmp && \ 
#     wget https://download.elastic.co/kibana/kibana/kibana-${KIBANA_VERSION}.tar.gz && \
#     tar -zxvf ./kibana-${KIBANA_VERSION}.tar.gz && \
#     mv ./kibana-${KIBANA_VERSION} ${KIBANA_SRC_DIR} && \
#     rm ./kibana-${KIBANA_VERSION}.tar.gz


ADD ./kibana-${KIBANA_VERSION}.tar.gz ${KIBANA_SRC_DIR}

WORKDIR ${KIBANA_SRC_DIR}/kibana-${KIBANA_VERSION}
COPY ./kibana.yml ./config/kibana.yml

ENTRYPOINT ["./bin/kibana"]
