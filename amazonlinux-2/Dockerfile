FROM amazonlinux:2

RUN yum -y update \
  && yum install -y \
    dbus \
    less \
    openssh-clients \
    openssh-server \
    python \
    sudo \
    which \
  && rm -rf /var/cache/yum

VOLUME ["/sys/fs/cgroup"]
CMD ["/usr/lib/systemd/systemd"]
