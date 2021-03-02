FROM nvidia/cuda:9.1-cudnn7-devel-ubuntu16.04

USER root

RUN apt-get update && apt-get install -yq --no-install-recommends \
    git \
    python-dev \
    python-pip \
    python-setuptools \
    python-opencv \
    python-tk \
    && apt-get clean && \
    rm -rf /var/lib/apt/lists/*

RUN pip install -U pip==19.3.1

RUN pip install torch==0.4.1 \
    torchvision==0.2.0 \
    cython \
    numpy==1.16.6 \
    pillow==4.3.0 \
    PyWavelets==1.0.3 \
    networkx==2.2 \
    matplotlib==2.1.2 \
    scipy==1.2.3 \
    scikit-image==0.14.2

RUN git clone https://github.com/tomoohive/superpixel_fcn.git

RUN cd ./superpixel_fcn/third_party/cython/ && python setup.py install --user
