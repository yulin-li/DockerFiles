FROM arm64v8/ubuntu:16.04

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
        wget \
        software-properties-common && \
        add-apt-repository ppa:ubuntu-toolchain-r/test -y && \
        apt-get update && \
        apt-get install gcc-6 g++-6 -y && \
        update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-6 60 --slave /usr/bin/g++ g++ /usr/bin/g++-6 && \
        rm -rf /var/lib/apt/lists/*

RUN wget --no-check-certificate https://cmake.org/files/v3.19/cmake-3.19.2.tar.gz \
        && tar xf cmake-3.19.2.tar.gz && \
        cd cmake-3.19.2 && \
        ./configure && \
        sudo make install -j8 && cd .. && rm -rf cmake-3.19*
