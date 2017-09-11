```dockerfile
# set the base image
FROM ubuntu:latest
# set who the author is of generated image
MAINTAINER Joseph Choi (chousemath@gmail.com)
# synchronize package lists
RUN yes Y | apt-get update
# install sudo
RUN yes Y | apt-get install sudo
# the following commands are for installation of gcc
# install the software-properties-common package for add-apt-repository
RUN yes Y | sudo apt-get install software-properties-common python-software-properties
# again, synchronize package lists just in case
RUN yes Y | sudo apt-get update
# install git
RUN yes Y | sudo apt-get install git
# install gcc (for Slic3r)
RUN yes Y | sudo add-apt-repository ppa:ubuntu-toolchain-r/test
# synchronize package lists
RUN yes Y | sudo apt-get update
# install gcc
RUN yes Y | sudo apt-get install gcc-5 g++-5
# set first priority to gcc-5
RUN yes Y | sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-5 1
# install perlbrew (a program that manages Perl installations)
RUN yes Y | apt-get install perlbrew
# initialize perlbrew
RUN perlbrew init
# append to .bashrc
RUN echo 'source ~/perl5/perlbrew/etc/bashrc' >> ~/.bashrc
# install libraries for Slic3r
RUN yes Y | sudo apt install build-essential libgtk2.0-dev libwxgtk3.0-dev libwx-perl libmodule-build-perl git cpanminus libextutils-cppguess-perl libboost-all-dev libxmu-dev liblocal-lib-perl wx-common libopengl-perl libwx-glcanvas-perl libtbb-dev
RUN yes Y | sudo apt-get install -y libxmu-dev freeglut3-dev libwxgtk-media3.0-dev
RUN yes Y | sudo apt-get install libboost-thread-dev libboost-system-dev libboost-filesystem-dev
# pull from Slic3r github stable
RUN git clone https://github.com/alexrj/Slic3r.git
WORKDIR /Slic3r
RUN git checkout -b origin/stable
# build Slic3r
RUN export LDLOADLIBS=-lstdc++
RUN perl Build.PL
# create a bash script to execute Slic3r
RUN touch slic3r
RUN echo '#!/bin/sh' >> ./slic3r
RUN echo 'perl ./slic3r.pl $*' >> ./slic3r
RUN chmod +x slic3r
RUN ./slic3r --help
```
