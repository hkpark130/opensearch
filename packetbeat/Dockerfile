# https://groups.google.com/g/wazuh/c/-3rL7zv1raA/m/_RVW-XVtBgAJ <- 참고
FROM ubuntu:20.04

# Install necessary packages
RUN apt-get update && apt-get install -y wget apt-transport-https

# Download Packetbeat OSS
RUN wget -qO packetbeat.tar.gz https://artifacts.elastic.co/downloads/beats/packetbeat/packetbeat-oss-7.12.1-linux-x86_64.tar.gz \
    && tar -xzf packetbeat.tar.gz \
    && rm packetbeat.tar.gz

# Copy your packetbeat configuration file into the container
COPY packetbeat.yml ./packetbeat-7.12.1-linux-x86_64/packetbeat.yml

RUN chmod go-w ./packetbeat-7.12.1-linux-x86_64/packetbeat.yml

RUN chmod +x ./packetbeat-7.12.1-linux-x86_64/packetbeat

# Start Packetbeat
CMD ["./packetbeat-7.12.1-linux-x86_64/packetbeat", "-e", "-c", "./packetbeat-7.12.1-linux-x86_64/packetbeat.yml"]
