# Dockerfile for building Android APK with Buildozer
FROM ubuntu:22.04

ENV DEBIAN_FRONTEND=noninteractive

# 安装系统依赖
RUN apt-get update && apt-get install -y \
    git \
    zip \
    unzip \
    openjdk-11-jdk \
    python3 \
    python3-pip \
    autoconf \
    libtool \
    pkg-config \
    zlib1g-dev \
    libncurses5-dev \
    libncursesw5-dev \
    libtinfo5 \
    cmake \
    libffi-dev \
    libssl-dev \
    build-essential \
    && rm -rf /var/lib/apt/lists/*

# 安装Buildozer和Cython
RUN pip3 install --upgrade pip && \
    pip3 install buildozer cython

# 设置工作目录
WORKDIR /app

# 复制项目文件
COPY . .

# 切换到Kalman目录
WORKDIR /app/Kalman

# 默认命令：构建APK
CMD ["buildozer", "android", "debug"]

