FROM ubuntu:16.04

RUN apt-get update && apt-get install --yes \
    apt-utils \
    curl \
    dbus \
    iproute2 \
    less \
    lsb-release \
    locales \
    openssh-server \
    python \
    python-virtualenv \
    rsyslog \
    sudo \
    systemd \
  && locale-gen en_US.UTF-8 \
  && rm -Rf /var/lib/apt/lists/*

ENV LANG=C.UTF-8

VOLUME ["/sys/fs/cgroup"]
CMD ["/lib/systemd/systemd"]
