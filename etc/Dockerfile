FROM ubuntu:14.04
MAINTAINER Dion Whitehead Amago

# Dependencies
RUN apt-get update
RUN apt-get install -y wget g++ g++-multilib libgc-dev git

# Download Haxe
RUN mkdir /root/haxe
#This is Haxe 3.2 if you need it. Change the URL for new versions.
ENV HAXE_DOWNLOAD_URL http://haxe.org/website-content/downloads/3.2.0/downloads/haxe-3.2.0-linux64.tar.gz
#Haxe 3.1
#ENV HAXE_DOWNLOAD_URL http://haxe.org/website-content/downloads/3,1,3/downloads/haxe-3.1.3-linux64.tar.gz

RUN wget -O - $HAXE_DOWNLOAD_URL | tar xzf - --strip=1 -C "/root/haxe"

# Download Neko
RUN mkdir /root/neko
RUN wget -O - http://nekovm.org/_media/neko-2.0.0-linux64.tar.gz | tar xzf - --strip=1 -C "/root/neko"

# Clean up APT when done.
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# Haxe environment variables
ENV HAXE_STD_PATH /root/haxe/std/
ENV PATH /root/haxe/:$PATH

# Neko environment variables
ENV NEKOPATH /root/neko/
ENV LD_LIBRARY_PATH /root/neko/
ENV PATH /root/neko/:$PATH

# Haxelib setup
RUN mkdir -p /project
WORKDIR /project
RUN haxelib newrepo
