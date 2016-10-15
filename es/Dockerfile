FROM elasticsearch:2.4
MAINTAINER Jan Nonnen <helvalius@gmail.com>

# Finalize elasticsearch installation
ADD config/elasticsearch.yml /usr/share/elasticsearch/config/

RUN mkdir -p /var/lib/elasticsearch/pelias_data \
  && chown -R elasticsearch:elasticsearch /var/lib/elasticsearch/pelias_data
RUN /usr/share/elasticsearch/bin/plugin install analysis-icu
ENV ES_HEAP_SIZE 4g
