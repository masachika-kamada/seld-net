FROM nvcr.io/nvidia/cuda:10.0-cudnn7-devel-ubuntu18.04

# 環境変数の設定
ENV DEBIAN_FRONTEND=noninteractive
ENV TZ Asia/Tokyo

# Python 3.7 PPAの追加
RUN apt-get update && apt-get install -y software-properties-common \
    && add-apt-repository -y ppa:deadsnakes/ppa \
    && apt-get update

# 必要なパッケージのインストール
RUN apt-get install -y \
    git \
    python3.7 \
    python3.7-venv \
    python3.7-dev \
    python3.7-distutils \
    curl \
    wget \
    fish \
    && ln -sf /usr/bin/python3.7 /usr/bin/python

# pipのインストール
RUN curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py \
    && python get-pip.py \
    && rm get-pip.py \
    && ln -sf /usr/local/bin/pip /usr/bin/pip \
    && rm -rf /var/lib/apt/lists/*
