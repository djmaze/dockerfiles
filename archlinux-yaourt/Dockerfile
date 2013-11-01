# Archlinux base image including yaourt
FROM archlinux

RUN pacman -Sy
RUN pacman -S --noconfirm --needed base-devel wget
RUN wget https://aur.archlinux.org/packages/pa/package-query/package-query.tar.gz && \
    tar -xvzf package-query.tar.gz && \
    cd package-query && \
    makepkg --asroot --noconfirm -si && \
    rm /package-query* -fR
RUN wget https://aur.archlinux.org/packages/ya/yaourt/yaourt.tar.gz && \
    tar -xvzf yaourt.tar.gz && \
    cd yaourt && \
    makepkg --asroot --noconfirm -si && \
    rm /yaourt* -fR
