FROM ubuntu:18.04 as ned-deb
LABEL maintainer="Nev Delap <nevdelap@gmail.com>"
RUN apt-get update && apt-get -y upgrade
RUN apt-get install -y debhelper debmake
RUN curl https://sh.rustup.rs -sSf | sh -s -- -y
RUN . /root/.cargo/env && rustup target add x86_64-unknown-linux-musl
WORKDIR /root/ned-deb
CMD . ~/.cargo/env && ./bbuild && \
    cp ned_1*-1_amd64.deb ~/artifacts

FROM ubuntu:18.04 as test-deb
LABEL maintainer="Nev Delap <nevdelap@gmail.com>"
RUN apt-get update && apt-get -y upgrade
RUN apt-get install -y man
RUN sed -Ei 's;(path-exclude=/usr/share/man/*);#\1;' /etc/dpkg/dpkg.cfg.d/excludes
WORKDIR /root/artifacts
