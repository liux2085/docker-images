FROM fedora:35

MAINTAINER Yongxin Liu <yongxin.liu@outlook.com>

ADD dumb-init_1.2.5_x86_64 /usr/bin/dumb-init

RUN \
    useradd --home-dir /home/yongxin --uid 1000 --gid 100 --shell /bin/bash yongxin && \
    echo "multilib_policy=best" >> /etc/dnf/dnf.conf && \
    echo "deltarpm=0" >> /etc/dnf/dnf.conf && \
    dnf -y --noplugins clean all && \
    dnf -y --noplugins install \
    SDL-devel \
    bzip2 \
    ccache \
    chrpath \
    cpio \
    cpp \
    curl \
    diffstat \
    diffutils \
    expect \
    file \
    findutils \
    gawk \
    gcc \
    gcc-c++ \
    git \
    glibc-devel.i686 \
    glibc-devel.x86_64 \
    glibc.i686 \
    glibc-langpack-en.x86_64 \
    gzip \
    help2man \
    hostname \
    libgcc.i686 \
    libgcc.x86_64 \
    libnsl2-devel \
    make \
    mesa-libGL \
    mesa-libGLU \
    ncurses-libs.i686 \
    openssh-server \
    patch \
    perl \
    perl-Data-Dumper \
    perl-Text-ParseWords \
    perl-Thread-Queue \
    perl-autodie \
    perl-bignum \
    perl-podlators \
    python2 \
    python3 \
    python3-pexpect \
    python3-pip \
    rpcgen \
    socat \
    screen \
    subversion \
    sudo \
    tar \
    texi2html \
    texinfo \
    time \
    unzip \
    wget \
    which \
    xz \
    git-lfs \
    lz4 \
    zstd \
    vim \
    meson \
    libvdpau* \
    glslang \
    libdrm* \
    llvm \
    llvm-devel.x86_64 \
    elfutils-libelf-devel \
    byacc \
    flex \
    wayland-* \
    libXext-devel \
    libXfixes-devel \
    libXxf86vm-devel \
    libXrandr-devel \
    strace \
    bison \
    gcc-gnat \
    openssl-devel \
    yum-utils && \
    dnf --noplugins clean all && \
    rm -rf /var/cache/dnf && \
    rm -rf /usr/share/{man,doc,info,gnome/help} && \
    rm -rf /usr/share/texlive/texmf-dist/{fonts,doc,tex} && \
    cd /usr/libexec/git-core && \
    find . -samefile git -name 'git-*' -exec ln -sf git {} \; && \
    cd / && git config --global --add sendemail.suppresscc all && \
    mkdir -p /home/yongxin/Projects && \
    echo "yongxin ALL=(ALL) NOPASSWD: ALL" >> /etc/sudoers && \
    chmod +x /usr/bin/dumb-init

ENTRYPOINT ["/bin/dumb-init"]

USER yongxin

CMD ["/bin/bash"]
