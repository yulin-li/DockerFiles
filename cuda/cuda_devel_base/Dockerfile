ARG CUDA="10.1"
ARG CUDNN="7"
FROM nvidia/cuda:${CUDA}-cudnn${CUDNN}-devel-ubuntu18.04

RUN apt-get update && apt-get install -y --no-install-recommends \
         build-essential \
         cmake \
         git \
         curl \
         ca-certificates \
         libjpeg-dev \
         libpng-dev \
         ca-certificates \
         wget \
         libsndfile-dev \
         sox \
         sudo \
         software-properties-common \
         python3-pip

# Install Open MPI
ENV OPENMPI_VERSIONBASE=4.0
ENV OPENMPI_VERSION=${OPENMPI_VERSIONBASE}.0
RUN mkdir /tmp/openmpi && \
    cd /tmp/openmpi && \
    wget https://www.open-mpi.org/software/ompi/v${OPENMPI_VERSIONBASE}/downloads/openmpi-${OPENMPI_VERSION}.tar.gz && \
    tar zxf openmpi-${OPENMPI_VERSION}.tar.gz && \
    cd openmpi-${OPENMPI_VERSION} && \
    ./configure --enable-orterun-prefix-by-default && \
    make -j $(nproc) all && \
    make install && \
    ldconfig && \
    rm -rf /tmp/openmpi

# install .Net Core SDK
# https://docs.microsoft.com/en-us/dotnet/core/install/linux-package-manager-ubuntu-1804
RUN wget -q https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb \
    && dpkg -i packages-microsoft-prod.deb \
    && rm -f packages-microsoft-prod.deb

RUN add-apt-repository universe && \
    apt-get update && apt-get install -y \
    apt-transport-https && \
    apt-get update && apt-get install -y \
    dotnet-sdk-3.1 \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /home/job/
RUN chmod -R a+w .