FROM ubuntu:xenial
RUN apt-get update \
    && apt-get install -y \
        git \
        wget \
        cmake \
        pkg-config \
        build-essential \
        autoconf \
        curl \
        libtool \
        unzip \
        flex \
        bison \
        zlib1g-dev \
    && apt-get clean \
    && echo 'export PATH=/opt/conda/bin:$PATH' > /etc/profile.d/conda.sh \
    && wget \
        --quiet 'https://repo.continuum.io/archive/Anaconda3-4.4.0-Linux-x86_64.sh' \
        -O /tmp/anaconda.sh \
    && /bin/bash /tmp/anaconda.sh -b -p /opt/conda \
    && rm /tmp/anaconda.sh \
    && /opt/conda/bin/conda install -y \
        libgcc \
        numpy \
    && /opt/conda/bin/conda clean -y --all \
    && /opt/conda/bin/pip install \
        flatbuffers \
        cython==0.27.3 \
        ray==0.5.2 \
        numpy \
        gym[atari] \
        opencv-python==3.2.0.8 \
        tensorflow \
    && /opt/conda/bin/pip install --upgrade git+git://github.com/hyperopt/hyperopt.git \
    && /opt/conda/bin/conda install pytorch-cpu torchvision-cpu -c pytorch

ENV PATH "/opt/conda/bin:$PATH"
ENV LC_ALL "C.UTF-8"
ENV LANG "C.UTF-8"
