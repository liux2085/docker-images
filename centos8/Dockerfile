FROM centos:8

MAINTAINER Yongxin Liu <yongxin.liu@outlook.com>

ADD dumb-init_1.2.5_x86_64 /usr/bin/dumb-init

RUN cd /etc/yum.repos.d/ && \
    sed -i 's/mirrorlist/#mirrorlist/g' /etc/yum.repos.d/CentOS-* && \
    sed -i 's|#baseurl=http://mirror.centos.org|baseurl=http://vault.centos.org|g' /etc/yum.repos.d/CentOS-* && \
    yum -y --noplugins clean all && \
    yum -y --noplugins install glibc.i686 glibc-devel.i686 glibc-devel.x86_64 libgcc.i686 \
    libgcc.x86_64 ncurses-libs.i686 perl-Text-ParseWords perl-podlators perl-autodie perl-bignum \
    perl-Thread-Queue diffstat subversion mesa-libGL mesa-libGLU SDL-devel \
    gawk gcc gcc-c++ chrpath git pygtk2 bzip2 wget tar patch xz perl-Digest-SHA \
    make diffutils file which sudo time python2 python3 vim libvdpau* libdrm* \
    llvm llvm-devel.x86_64 elfutils-libelf-devel byacc flex wayland-* libXext-devel libXfixes-devel \
    libXxf86vm-devel libXrandr-devel strace yum-utils perl-Data-Dumper* && \
    useradd --home-dir /home/yongxin --uid 1000 --gid 100 --shell /bin/bash yongxin && \
    echo "yongxin ALL=(ALL) NOPASSWD: ALL" >> /etc/sudoers && \
    yum --noplugins clean all && \
    rm -rf /var/cache/yum && \
    rm -rf /usr/share/man && \
    rm -rf /usr/share/doc && \
    rm -rf /usr/share/texlive/texmf-dist/{fonts,doc,tex} && \
    cd /usr/libexec/git-core && \
    find . -samefile git -name 'git-*' -exec ln -sf git {} \; && \
    cd / && git config --global --add sendemail.suppresscc all && \
    localedef --list-archive | grep -v -i ^en | xargs localedef --delete-from-archive && \
    mv /usr/lib/locale/locale-archive /usr/lib/locale/locale-archive.tmpl && \
    build-locale-archive && \
    rm /usr/lib/locale/locale-archive.tmpl && \
    chmod +x /usr/bin/dumb-init

ENTRYPOINT ["/usr/bin/dumb-init"]

USER yongxin

CMD ["/bin/bash"]

