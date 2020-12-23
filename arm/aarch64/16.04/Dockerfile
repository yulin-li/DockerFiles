
FROM arm64v8/ubuntu:16.04

RUN apt-get update && apt-get install -y --no-install-recommends \
        sudo \
        automake \
        libtool-bin \
        sqlite \
        curl \
        libcurl4-openssl-dev \
        zlib1g-dev \
        git \
        build-essential \
        libssl-dev \
        libsqlite3-dev \
        wget && rm -rf /var/lib/apt/lists/*

RUN wget https://cmake.org/files/v3.19/cmake-3.19.2.tar.gz \
        && tar xf cmake-3.19.2.tar.gz && \
        cd cmake-3.19.2 && \
        ./configure && \
        sudo make install -j8 && cd .. && rm -rf cmake-3.19*
