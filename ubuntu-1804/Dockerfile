FROM ubuntu:18.04

RUN apt-get update \
  && apt-get install --yes --no-install-recommends \
    apt-utils \
    curl \
    dbus \
    iproute2 \
    less \
    lsb-release \
    locales \
    openssh-server \
    python3 \
    python3-pip \
    virtualenv \
    rsyslog \
    sudo \
    systemd \
  && locale-gen en_US.UTF-8 \
  && rm -Rf /var/lib/apt/lists/*

ENV LANG=C.UTF-8

VOLUME ["/sys/fs/cgroup"]
CMD ["/lib/systemd/systemd"]
