FROM python:3.6.8

RUN sed -i s/archive.ubuntu.com/free.nchc.org.tw/g /etc/apt/sources.list && \
    echo "deb http://security.ubuntu.com/ubuntu xenial-security main" >> /etc/apt/sources.list && \
    apt-get update && apt install -y cmake

RUN pip install opencv-python dlib face_recognition requests onnxruntime
