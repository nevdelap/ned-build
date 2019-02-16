FROM archlinux/base:latest as ned-aur
LABEL maintainer="Nev Delap <nevdelap@gmail.com>"
RUN pacman -Syu --noconfirm
RUN pacman -S --noconfirm base-devel rust
RUN useradd build -m
CMD su - build -c "cd ned-aur && makepkg -f"; \
    cp /home/build/ned-aur/pkg/ned/usr/bin/ned /home/build/artifacts && \
    cp /home/build/ned-aur/pkg/ned/usr/share/man/man1/ned.1.gz /home/build/artifacts

FROM archlinux/base:latest as test-aur
LABEL maintainer="Nev Delap <nevdelap@gmail.com>"
RUN pacman -Syu --noconfirm
RUN pacman -S --noconfirm man
WORKDIR /root/artifacts
