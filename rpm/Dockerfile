FROM centos:7 as ned-rpm
LABEL maintainer="Nev Delap <nevdelap@gmail.com>"
RUN yum update -y
RUN yum install -y epel-release gcc git man nano rpmdevtools
RUN echo insecure >> ~/.curlrc
RUN curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- -y
RUN . ~/.cargo/env && rustup target add x86_64-unknown-linux-musl
WORKDIR /root/rpmbuild/SPECS
# -D 'debug_package %{nil} is to work around debugedit: canonicalization unexpectedly shrank by one character, a bug
# apparently originally reported in 2007 and still around.
CMD spectool -g -R ned.spec && \
    rpmbuild -ba ned.spec -D 'debug_package %{nil}'; \
    cp ../RPMS/x86_64/ned-1*.rpm ~/artifacts

FROM centos:7 as test-rpm
LABEL maintainer="Nev Delap <nevdelap@gmail.com>"
RUN yum update -y
RUN yum install -y man
WORKDIR /root/artifacts
