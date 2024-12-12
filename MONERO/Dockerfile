FROM ubuntu:18.04

RUN apt-get update && apt-get install -y \
    wget \
    supervisor && \
    rm -rf /var/lib/apt/lists/*

WORKDIR /usr/local/bin

RUN wget https://downloads.getmonero.org/linux64 -O monero.tar.bz2 && \
    tar -jvxf monero.tar.bz2 -C . && \
    rm monero.tar.bz2  && \
    cp monero-x86_64-linux-gnu-v*/* .

RUN mkdir -p /var/log/supervisor /root/.bitmonero /wallet /config

EXPOSE 18080 18081 18083

COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf

VOLUME ["/root/.bitmonero", "/wallet", "/config"]

ENTRYPOINT ["/usr/bin/supervisord"]