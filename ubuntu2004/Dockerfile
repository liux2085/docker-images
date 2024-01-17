FROM ubuntu:20.04

MAINTAINER Yongxin Liu <yongxin.liu@outlook.com>

ADD dumb-init_1.2.5_x86_64 /usr/bin/dumb-init

RUN \
    apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get -o Dpkg::Options::="--force-confnew" -qy install --no-install-recommends \
    texi2html chrpath \
    diffstat subversion libgl1-mesa-dev libglu1-mesa-dev libsdl1.2-dev \
    texinfo gawk gcc gcc-multilib help2man g++ git-core bash cpio python \
    python3 python3-pip python3-pexpect debianutils iputils-ping locales \
    diffutils xz-utils make file screen sudo wget time patch openssh-client curl vim vim-tiny \
    iproute2 iputils-ping unzip texinfo build-essential socat python3-git python3-jinja2 libegl1-mesa \
    nasm libxcb1 libfontconfig1 libxcb-icccm4 libxcb-image0 libxcb-keysyms1 libxcb-randr0 libxcb-render-util0 \
    libxcb-shape0 libxcb-sync1 libxcb-xfixes0 libxcb-xinerama0 libxkbcommon-x11-0 unzip build-essential \
    iasl python-is-python3 uuid-dev nasm openssl gcc-multilib git m4 bison flex qemu-system-x86 \
    pylint3 uuid-runtime rsync libelf-dev libssl-dev bc meson flex bison libnl* git-lfs && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* && \
    rm -rf /usr/share/man && \
    rm -rf /usr/share/doc && \
    rm -rf /usr/share/grub2 && \
    rm -rf /usr/share/texmf/fonts && \
    rm -rf /usr/share/texmf/doc && \
    locale-gen en_US.UTF-8 && \
    update-locale LANG=en_US.UTF-8 && \
    useradd --home-dir /home/yongxin --uid 1000 --gid 100 --shell /bin/bash yongxin && \
    mkdir -p /home/yongxin/Projects && \
    echo "yongxin ALL=(ALL) NOPASSWD: ALL" >> /etc/sudoers && \
    chmod +x /usr/bin/dumb-init

ENTRYPOINT ["/usr/bin/dumb-init"]

CMD ["/bin/bash"]

USER yongxin
