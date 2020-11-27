FROM nvidia/cuda:11.0-cudnn8-devel-ubuntu18.04

LABEL maintainer="Kelvin Wu <kelvinyu1117@gmail.com>" 
ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update && apt-get install -y --no-install-recommends \
    build-essential \
    cmake \
    git \
    wget \
    python-dev \
    python-pip \
    tzdata \
    vim


# RUN apt-get update && apt-get install libgl1-mesa-glx libegl1-mesa libxrandr2 libxrandr2 libxss1 libxcursor1 libxcomposite1 libasound2 libxi6 libxtst6

RUN wget --quiet https://repo.anaconda.com/archive/Anaconda3-2020.11-Linux-x86_64.sh -O ~/anaconda.sh && \
    /bin/bash ~/anaconda.sh -b -p /opt/conda && \
    rm ~/anaconda.sh && \
    echo "export PATH=/opt/conda/bin:$PATH" >> ~/.bashrc \
    conda install pytorch torchvision torchaudio cudatoolkit=10.2 -c pytorch


RUN mkdir /workspace
WORKDIR /workspace
