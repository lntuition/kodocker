FROM ubuntu:latest

MAINTAINER Sang-Heon Jeon "ekffu200098@gmail.com"

# Install pyenv : https://github.com/pyenv/pyenv,
# Install pyenv-virtualenv : https://github.com/pyenv/pyenv-virtualenv
# Install tox : https://github.com/tox-dev/tox/
# Related tortoise-orm : https://github.com/tortoise/tortoise-orm

ENV DEBIAN_FRONTEND=noninteractive
ENV LANG="C.UTF-8"
ENV LC_ALL="C.UTF-8"
ENV HOME=/root
ENV PYENV_ROOT=$HOME/.pyenv
ENV PATH=$PYENV_ROOT/bin:$PATH
ENV TORTOISE_HOME=/storage/tortoise-orm

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

ARG PYTHON37_VERSION=3.7.6
ARG PYTHON38_VERSION=3.8.1
ARG PYTHON39_VERSION=3.9-dev

RUN pyenv install $PYTHON37_VERSION
RUN pyenv install $PYTHON38_VERSION
RUN pyenv install $PYTHON39_VERSION
RUN pyenv virtualenv -p python3.7 $PYTHON37_VERSION py37
RUN pyenv virtualenv -p python3.8 $PYTHON38_VERSION py38
RUN pyenv virtualenv -p python3.9 $PYTHON39_VERSION py39
RUN pyenv global py37 py38 py39

RUN mkdir -p $TORTOISE_HOME
COPY tortoise-orm $TORTOISE_HOME
WORKDIR $TORTOISE_HOME
RUN pyenv exec pip install pytest
RUN pyenv exec pip install -r tests/requirements.txt
