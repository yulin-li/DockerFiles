FROM arm64v8/ubuntu:18.04

RUN apt-get update && apt-get install -y --no-install-recommends \
        sudo \
        automake \
        libtool-bin \
        sqlite \
        curl \
        libcurl4-openssl-dev \
        ca-certificates \
        zlib1g-dev \
        uuid-dev \
        git \
        build-essential \
        libssl-dev \
        libsqlite3-dev \
        alsa \
        libasound2-dev \
        pkg-config \
        wget && \
        rm -rf /var/lib/apt/lists/*

ENV CMAKE_VERSION=3.20.2
RUN wget --no-check-certificate https://cmake.org/files/v${CMAKE_VERSION%.*}/cmake-${CMAKE_VERSION}.tar.gz \
        && tar xf cmake-${CMAKE_VERSION}.tar.gz && \
        cd cmake-${CMAKE_VERSION} && \
        ./configure && \
        sudo make install -j8 && cd .. && rm -rf cmake-${CMAKE_VERSION}*
