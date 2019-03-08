FROM centos:7

RUN yum -y update \
  && yum install -y \
    dbus \
    less \
    openssh-clients \
    openssh-server \
    python \
    sudo \
    which \
  && yum clean all

VOLUME ["/sys/fs/cgroup"]
CMD ["/usr/lib/systemd/systemd"]
