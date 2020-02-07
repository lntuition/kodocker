FROM ubuntu:latest

MAINTAINER Sang-Heon Jeon "ekffu200098@gmail.com"

# Install pyenv : https://github.com/pyenv/pyenv,
# Install pyenv-virtualenv : https://github.com/pyenv/pyenv-virtualenv
# Install tox : https://github.com/tox-dev/tox/
ENV DEBIAN_FRONTEND=noninteractive
ENV HOME=/root
ENV PYENV_ROOT=$HOME/.pyenv
ENV PATH=$PYENV_ROOT/bin:$PATH
ENV LC_ALL=C.UTF-8
ENV LANG=C.UTF-8

RUN apt-get update && apt-get install -y \
        ca-certificates make build-essential libssl1.0-dev \
        zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev \
        wget curl llvm libncurses5-dev libncursesw5-dev \
        xz-utils tk-dev libffi-dev liblzma-dev \
        python-openssl git python3 python3-pip
RUN pip3 install setuptools tox tox-pyenv

RUN git clone https://github.com/pyenv/pyenv.git $PYENV_ROOT
RUN git clone https://github.com/pyenv/pyenv-virtualenv.git $PYENV_ROOT/plugins/pyenv-virtualenv
RUN echo 'if command -v pyenv 1>/dev/null 2>&1; then\n  eval "$(pyenv init -)"\nfi' >> ~/.bashrc
RUN echo 'eval "$(pyenv virtualenv-init -)"' >> ~/.bashrc

ARG PYTHON27_VERSION=2.7.15
ARG PYTHON33_VERSION=3.3.7
ARG PYTHON34_VERSION=3.4.10
ARG PYTHON35_VERSION=3.5.9
ARG PYTHON36_VERSION=3.6.10
ARG PYTHON37_VERSION=3.7.6
ARG PYTHON38_VERSION=3.8.1
ARG PYPY3_VERSION=pypy3.6-7.3.0

RUN pyenv install $PYTHON27_VERSION
RUN pyenv install $PYTHON33_VERSION
RUN pyenv install $PYTHON34_VERSION
RUN pyenv install $PYTHON35_VERSION
RUN pyenv install $PYTHON36_VERSION
RUN pyenv install $PYTHON37_VERSION
RUN pyenv install $PYTHON38_VERSION
RUN pyenv install $PYPY3_VERSION

RUN pyenv global $PYTHON27_VERSION \ 
        $PYTHON33_VERSION \
        $PYTHON34_VERSION \
        $PYTHON35_VERSION \
        $PYTHON36_VERSION \
        $PYTHON37_VERSION \
        $PYTHON38_VERSION \
        $PYPY3_VERSION

RUN mkdir /storage
WORKDIR /storage
