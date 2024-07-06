FROM ubuntu:20.04

RUN apt-get update && \
    apt-get install -y wget tar && \
    rm -rf /var/lib/apt/lists/*

RUN wget https://artifacts.opensearch.org/releases/bundle/opensearch-dashboards/1.3.6/opensearch-dashboards-1.3.6-linux-x64.tar.gz && \
    tar -zxf opensearch-dashboards-1.3.6-linux-x64.tar.gz && \
    rm opensearch-dashboards-1.3.6-linux-x64.tar.gz

COPY opensearch_dashboards.yml ./opensearch-dashboards-1.3.6/config/opensearch_dashboards.yml

CMD ["./opensearch-dashboards-1.3.6/bin/opensearch-dashboards", "--allow-root"]
