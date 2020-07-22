FROM centos:8

RUN yum -y update \
  && yum install -y \
    dbus \
    less \
    openssh-clients \
    openssh-server \
    python-virtualenv \
    python3 \
    python3-pip \
    sudo \
    which \
  && rm -rf /var/cache/yum

VOLUME ["/sys/fs/cgroup"]
CMD ["/usr/lib/systemd/systemd"]
