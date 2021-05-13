FROM archlinux/archlinux:latest as ned-aur
LABEL maintainer="Nev Delap <nevdelap@gmail.com>"
RUN pacman -Sy --needed --noconfirm base-devel rust
RUN useradd build -m
CMD su - build -c "cd ned-aur && makepkg -f"; \
    cp /home/build/ned-aur/pkg/ned/usr/bin/ned /home/build/artifacts && \
    cp /home/build/ned-aur/pkg/ned/usr/share/man/man1/ned.1.gz /home/build/artifacts

FROM archlinux/archlinux:latest as test-aur
LABEL maintainer="Nev Delap <nevdelap@gmail.com>"
RUN pacman -Sy --needed --noconfirm base-devel binutils fakeroot git go man sudo
RUN useradd -m -s /bin/sh build && \
    passwd -d build && \
    echo 'build ALL=(ALL) ALL' > /etc/sudoers.d/build
WORKDIR /home/build
RUN sudo -u build git clone https://aur.archlinux.org/yay.git
WORKDIR /home/build/yay
RUN sudo -u build makepkg -si --noconfirm
RUN sed -Ei 's;(NoExtract *= *usr/share/man[^\n]+);#\1;' /etc/pacman.conf
WORKDIR /home/build/ned-aur
