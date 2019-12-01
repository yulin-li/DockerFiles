FROM nvidia/cuda:9.2-cudnn7-runtime-ubuntu18.04

RUN apt-get update && apt-get install -y \
    sudo \
    wget

# install .Net Core SDK
# https://docs.microsoft.com/en-us/dotnet/core/install/linux-package-manager-ubuntu-1804

RUN wget -q https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
RUN dpkg -i packages-microsoft-prod.deb

RUN rm -f packages-microsoft-prod.deb

RUN add-apt-repository universe
RUN apt-get update && apt-get install -y \
    apt-transport-https 
RUN apt-get update && apt-get install -y \
    dotnet-sdk-3.0 \
    && rm -rf /var/lib/apt/lists/*