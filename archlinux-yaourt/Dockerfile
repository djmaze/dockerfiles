# Archlinux base image including yaourt
FROM archlinux

# Install yaourt
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

# Workaround for gpgme
RUN echo -e \ 
    "#!/bin/sh \
    \n# Workaround to get gpgme and pacman working, see https://github.com/dotcloud/docker/issues/728#issuecomment-21192342 \
    \nexec >/dev/tty 2>/dev/tty </dev/tty" >~/.bashrc && \
    ln -s ~/.bashrc ~/.bash_profile

# Another workaround
RUN ln -s /proc/self/fd /dev/fd

# Launch a shell by default
CMD ["/bin/bash"]
