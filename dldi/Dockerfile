FROM --platform=linux/amd64 debian:bullseye-slim

RUN apt-get update && apt-get install -y wget unzip && wget https://www.chishm.com/DLDI/downloads/dlditool-linux-x86_64.zip -O dlditool.zip && unzip dlditool.zip && \
    mv dlditool /bin/. && \
    apt-get clean
