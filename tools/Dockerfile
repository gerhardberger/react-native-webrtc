FROM debian:stable-slim

ENV DEBIAN_FRONTEND=noninteractive

#This is required fo bypassing the tzdata installation
ENV TZ=Europe/Bucharest
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

RUN apt-get update
RUN apt-get install -y sudo
RUN apt-get install -y git
RUN apt-get install -y python
RUN apt-get install -y curl
RUN apt-get install -y lsb-release
RUN apt-get install -y vim
RUN apt-get install -y ninja-build
RUN apt-get install -y pkg-config
RUN apt-get install -y gcc-arm-linux-gnueabihf
RUN apt-get install -y g++-8-arm-linux-gnueabihf

#Install JAVA
RUN mkdir -p /usr/share/man/man1
WORKDIR /opt
RUN apt-get update \
    && apt-get install -y --no-install-recommends \
        ca-certificates \
        curl \
    && curl \
        -L \
        -o openjdk.tar.gz \
        https://download.java.net/java/GA/jdk11/13/GPL/openjdk-11.0.1_linux-x64_bin.tar.gz \
    && mkdir jdk \
    && tar zxf openjdk.tar.gz -C jdk --strip-components=1 \
    && ln -sf /opt/jdk/bin/* /usr/local/bin/

# clone react-native-webrtc repository
WORKDIR /
RUN git clone https://github.com/react-native-webrtc/react-native-webrtc.git
