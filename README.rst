
Docker build files for Yongxin
==============================

dumb-init_1.2.5_x86_64 from https://github.com/Yelp/dumb-init/releases

CentOS 8 
--------
    Build command: docker build -f ./Dockerfile -t yx_centos8:latest .

    Run command: docker run -i -t -v /home/yongxin/Projects:/home/yongxin/Projects -u yongxin yx_centos8

Ubuntu 20.04
------------
    Build command: docker build -f ./Dockerfile -t yx_ubuntu2004:latest .

    Run command: docker run -i -t -v /home/yongxin/Projects:/home/yongxin/Projects -u yongxin yx_ubuntu2004

Fedora 35
---------
    Build command: docker build -f ./Dockerfile -t yx_fedora35:latest .

    Run command: docker run -i -t -v /home/yongxin/Projects:/home/yongxin/Projects -u yongxin yx_fedora35
