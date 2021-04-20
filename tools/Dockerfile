FROM debian:stable-slim

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

#Install JRE
RUN mkdir -p /usr/share/man/man1 /usr/share/man/man2
RUN apt-get install -y --no-install-recommends openjdk-11-jre

# clone react-native-webrtc repository
RUN git clone https://github.com/react-native-webrtc/react-native-webrtc.git

