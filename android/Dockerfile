FROM ubuntu:12.04

MAINTAINER Darren "dyhpoon@gmail.com"

RUN apt-get update -qq

# Dependencies to execute android
RUN apt-get install -y --no-install-recommends openjdk-7-jdk libgd2-xpm ia32-libs ia32-libs-multiarch

# Main Android SDK
RUN apt-get install -y --no-install-recommends wget
RUN cd /opt && wget -q http://dl.google.com/android/android-sdk_r24.1.2-linux.tgz
RUN cd /opt && tar xzf android-sdk_r24.1.2-linux.tgz
RUN cd /opt && rm -f android-sdk_r24.1.2-linux.tgz

# SET ENV
ENV ANDROID_HOME /opt/android-sdk-linux
ENV PATH ${PATH}:${ANDROID_HOME}/tools:${ANDROID_HOME}/platform-tools

# Other tools and APIs
RUN echo y | android update sdk --filter platform-tools,extra-android-support --no-ui --force
RUN echo y | android update sdk --filter build-tools-22.0.1,build-tools-22,build-tools-21.1.2,build-tools-21.1.1,build-tools-21.1,build-tools-21.0.2,build-tools-21.0.1,build-tools-21,build-tools-20 --no-ui --force --all
RUN echo y | android update sdk --filter android-22,android-21 --no-ui --force --all

# Git to pull external repositories of Android app projects
RUN apt-get install -y --no-install-recommends git

# Cleaning
RUN apt-get clean