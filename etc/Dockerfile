# Use phusion/baseimage as base image. To make your builds
# reproducible, make sure you lock down to a specific version, not
# to `latest`! See
# https://github.com/phusion/baseimage-docker/blob/master/Changelog.md
# for a list of version numbers.
# See http://phusion.github.io/baseimage-docker/
#FROM phusion/baseimage:0.9.16
FROM ubuntu:14.04
MAINTAINER Dion Whitehead Amago

# Use baseimage-docker's init system.
# CMD ["/sbin/my_init"]

# ...put your own build instructions here...
# Dependencies
RUN apt-get update
RUN apt-get install -y wget g++ g++-multilib libgc-dev

# Download Haxe
RUN mkdir /root/haxe
#This is Haxe 3.2 if you need it. Change the URL for new versions.
#RUN wget -O - http://hxbuilds.s3-website-us-east-1.amazonaws.com/builds/haxe/linux64/haxe_2015-01-03_development_48dbf28.tar.gz | tar xzf - --strip=1 -C "/root/haxe"
# But we're using latest stable Haxe 3.1.3
RUN wget -O - http://haxe.org/website-content/downloads/3,1,3/downloads/haxe-3.1.3-linux64.tar.gz | tar xzf - --strip=1 -C "/root/haxe"

# Download Neko
RUN mkdir /root/neko
RUN wget -O - http://nekovm.org/_media/neko-2.0.0-linux64.tar.gz | tar xzf - --strip=1 -C "/root/neko"

# Haxe environment variables
ENV HAXE_STD_PATH /root/haxe/std/
ENV PATH /root/haxe/:$PATH

# Neko environment variables
ENV NEKOPATH /root/neko/
ENV LD_LIBRARY_PATH /root/neko/
ENV PATH /root/neko/:$PATH

# Haxelib setup
RUN mkdir /project
RUN echo /project/haxe_modules > /root/.haxelib
RUN cp /root/.haxelib /etc/

# Clean up APT when done.
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*









