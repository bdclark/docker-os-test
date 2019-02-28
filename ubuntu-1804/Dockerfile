FROM ubuntu:18.04

RUN apt-get update && apt-get install --yes \
    apt-utils \
    curl \
    iproute2 \
    less \
    lsb-release \
    openssh-server \
    python \
    python-virtualenv \
    rsyslog \
    sudo \
    systemd \
  && rm -Rf /var/lib/apt/lists/*

ENV LANG=C.UTF-8

VOLUME ["/sys/fs/cgroup"]
CMD ["/lib/systemd/systemd"]
