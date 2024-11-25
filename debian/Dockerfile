FROM debian:stable-slim

LABEL maintainer="by275"
LABEL org.opencontainers.image.source=https://github.com/by275/docker-open-vm-tools

COPY root/ /

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
        openssh-client \
        open-vm-tools \
        tini \
    && \
    chmod 755 /entrypoint.sh /usr/sbin/shutdown && \
    rm -rf /var/lib/apt/lists/*

CMD ["/usr/bin/tini", "--", "/entrypoint.sh"]
