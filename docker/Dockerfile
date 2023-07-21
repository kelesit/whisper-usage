FROM pytorch/pytorch:1.13.1-cuda11.6-cudnn8-runtime

ENV DEBIAN_FRONTEND=noninteractive 

ENV NVIDIA_VISIBLE_DEVICES all 
ENV NVIDIA_DRIVER_CAPABILITIES graphics,compute,utility,video

RUN printf "deb http://mirrors.tencentyun.com/ubuntu/ focal main multiverse restricted universe \ndeb http://mirrors.tencentyun.com/ubuntu/ focal-backports main multiverse restricted universe \ndeb http://mirrors.tencentyun.com/ubuntu/ focal-proposed main multiverse restricted universe \ndeb http://mirrors.tencentyun.com/ubuntu/ focal-security main multiverse restricted universe \ndeb http://mirrors.tencentyun.com/ubuntu/ focal-updates main multiverse restricted universe \ndeb-src http://mirrors.tencentyun.com/ubuntu/ focal main multiverse restricted universe \ndeb-src http://mirrors.tencentyun.com/ubuntu/ focal-backports main multiverse restricted universe \ndeb-src http://mirrors.tencentyun.com/ubuntu/ focal-proposed main multiverse restricted universe \ndeb-src http://mirrors.tencentyun.com/ubuntu/ focal-security main multiverse restricted universe \ndeb-src http://mirrors.tencentyun.com/ubuntu/ focal-updates main multiverse restricted universe" > /etc/apt/sources.list

RUN pip3 config set global.index-url http://pypi.devops.xiaohongshu.com/simple/
RUN pip3 config set install.trusted-host pypi.devops.xiaohongshu.com

RUN apt-get update -y --fix-missing  && apt-get install -y --allow-downgrades --no-install-recommends  \
        apt-utils build-essential \
        clang \
        gdb  \
        lld patchelf \
        htop iftop tmux lsof numactl libxml2 \
        git git-lfs wget vim openssh-client less tree curl unzip  libc-ares-dev libc-ares2 zlib1g-dev libssl-dev m4 make \
        libgtest-dev net-tools \
        libboost-filesystem-dev \
        libboost-system-dev \
        libgflags-dev \
        libgoogle-glog-dev \
        libopenblas-dev \
        libyaml-cpp-dev \
        libomp-dev \
        libopencv-dev \
        libgflags-dev libprotobuf-dev libprotoc-dev protobuf-compiler libleveldb-dev \
        libsnappy-dev \
        libevent-dev pkg-config \
        linux-tools-common \
        python3-distutils python3-dev python3-pip \
        linux-tools-generic \
        libcurl4-openssl-dev \
        ant libboost-dev libboost-test-dev libboost-program-options-dev libboost-thread-dev  automake  flex bison libtool \
        libpoco-dev \
        yasm \
        python3-tk \
        libhiredis-dev \
        redis-tools \
        iputils-ping \
        ffmpeg nvidia-cuda-dev \
        libjsoncpp-dev libboost-log-dev libboost-chrono-dev libboost-date-time-dev libboost-serialization-dev libboost-locale-dev libboost-iostreams-dev \
        && rm -rf /var/lib/apt/lists/*

RUN pip install --no-cache-dir -U openai-whisper packaging ninja