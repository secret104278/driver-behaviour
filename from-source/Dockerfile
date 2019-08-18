FROM ubuntu:18.04

RUN sed -i s/archive.ubuntu.com/free.nchc.org.tw/g /etc/apt/sources.list && \
    echo "deb http://security.ubuntu.com/ubuntu xenial-security main" >> /etc/apt/sources.list && \
    apt-get update && apt-get upgrade -y && \
    apt install -y \
    vim less git python3 python3-pip python3-dev python3-numpy gcc g++ cmake ccache \
    libjasper1 libjasper-dev libopenblas-dev \
    libjpeg-turbo8-dev libpng-dev libtiff-dev \
    libopenexr-dev libtiff-dev libwebp-dev \
    libgtk-3-dev \
    libavcodec-dev libavformat-dev libswscale-dev libavresample-dev libdc1394-22-dev \
    libgstreamer-plugins-base1.0-dev libgstreamer1.0-dev && \
    rm -rf /var/lib/apt/lists/*

RUN cd && git clone https://github.com/opencv/opencv.git && cd opencv && \
    git checkout 4.1.1 && mkdir build && cd build && \
    cmake ../ && make && make install && cd && rm -rf opencv

RUN cd && git clone -b 'v19.17' --single-branch https://github.com/davisking/dlib.git && \
    cd dlib && \
    python3 setup.py install && cd && rm -rf dlib