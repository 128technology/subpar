FROM ubuntu:xenial

# Touch this to update all apt packages
ENV REFRESHED_AT 2016-10-11:17:20:00

# So we can update apt repositories
RUN apt-get update -q && apt-get install -qy \
    apt-transport-https \
    curl \
    git \
    python \
    python3 \
    software-properties-common

# JDK is no longer required since there is one bundled with Bazel

# Install Bazel.  Instructions from https://www.bazel.io/versions/master/docs/install.html
RUN echo "deb [arch=amd64] http://storage.googleapis.com/bazel-apt stable jdk1.8" \
    | tee /etc/apt/sources.list.d/bazel.list \
    && curl https://storage.googleapis.com/bazel-apt/doc/apt-key.pub.gpg \
    | apt-key add -
RUN apt-get update -q && apt-get install -qy \
    bazel
