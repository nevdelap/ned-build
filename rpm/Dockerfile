FROM centos:7 as ned-rpm
LABEL maintainer="Nev Delap <nevdelap@gmail.com>"
RUN yum update -y
RUN yum install -y epel-release git man nano rpmdevtools
RUN yum install -y cargo rust
WORKDIR /root/rpmbuild/SPECS
CMD chown root:root ned.spec && \
    spectool -g -R ned.spec && \
    rpmbuild -ba ned.spec; \
    chown 1000:1000 ned.spec; \
    cp ../RPMS/x86_64/ned-1*.rpm ~/artifacts

FROM centos:7 as test-rpm
LABEL maintainer="Nev Delap <nevdelap@gmail.com>"
RUN yum update -y
RUN yum install -y man
WORKDIR /root/artifacts
