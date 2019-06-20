# Docker Images OS Testing

Various OS images with additional packages added to make them useful for
testing Ansible roles, etc. along with tools like Test-Kitchen or Molecule.

### Images built using this repo
- `bdclark/ubuntu-1804-test` - derived from `ubuntu:18.04` official image
- `bdclark/ubuntu-1604-test` - derived from `ubuntu:16.04` official image
- `bdclark/centos-7` - derived from `centos:7` official image
- `bdclark/amazonlinux-2-test` - derived from `amazonlinux:2` official image

### Usage example
The images all have systemd installed and are expected to be used in a way
where systemd is running as pid 1 for testing services.

Here's an example docker run command using systemd as pid 1:
```shell
docker run --detach \
  --cap-add SYS_ADMIN \
  --tmpfs /run --tmpfs /run/lock \
  --volume /sys/fs/cgroup:/sys/fs/cgroup:ro \
  --stop-signal "SIGRTMIN+3" \
  bdclark/ubuntu-1804-test /lib/systemd/systemd
```

See my [Jenkins Ansible role][2] for an example of how to use these images
for testing an Ansible role using [Test-Kitchen][1] on TravisCI.

### Ansible not installed
Please note that Ansible is NOT installed on these images. This allows them to
be used to test against various versions of Ansible without maintaining
version-specific images.

[1]:https://kitchen.ci/
[2]:https://github.com/bdclark/ansible-jenkins
