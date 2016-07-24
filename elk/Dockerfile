FROM daocloud.io/library/ubuntu:latest

RUN apt-get update
RUN apt-get install -y wget build-essential \
  apt-transport-https curl git libssl-dev python rsync

WORKDIR /elk

# RUN wget https://download.elastic.co/elasticsearch/release/org/elasticsearch/distribution/tar/elasticsearch/2.3.4/elasticsearch-2.3.4.tar.gz
# RUN wget https://download.elastic.co/logstash/logstash/logstash-2.3.4.tar.gz
# RUN wget https://download.elastic.co/kibana/kibana/kibana-4.5.3-linux-x64.tar.gz

ADD ./elasticsearch-2.3.4.tar.gz /elk/
ADD ./logstash-2.3.4.tar.gz /elk/
ADD ./kibana-4.5.3-linux-x64.tar.gz /elk/

# RUN tar -zxvf elasticsearch-2.3.4.tar.gz
# RUN tar -zxvf logstash-2.3.4.tar.gz
# RUN tar -zxvf kibana-4.5.3-linux-x64.tar.gz

COPY ./logstash.conf /elk/logstash-2.3.4.tar.gz/config/

EXPOSE 5601:5601

CMD /elk/elasticsearch-2.3.4/bin/elasticsearch -d  \ 
    && /elk/logstash-2.3.4/bin/logstash -f /elk/logstash-2.3.4/config/logstash.conf -d  \ 
    && /elk/kibana-4.5.3/bin/kibana -d
