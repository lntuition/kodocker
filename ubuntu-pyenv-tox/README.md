# Ubuntu-pyenv-tox
Image for development python library.
This image include pyenv and tox.

## How to use
1. Customize args to control pyenv python version

|Argument name   |default      |
|----------------|-------------|
|PYTHON27_VERSION|2.7.15       |
|PYTHON34_VERSION|3.4.10       |
|PYTHON35_VERSION|3.5.9        |
|PYTHON36_VERSION|3.6.10       |
|PYTHON37_VERSION|3.7.6        |
|PYTHON38_VERSION|3.8.1        |
|PYPY3_VERSION   |pypy3.6-7.3.0|

2. Build image
```console
$ docker-compose build
```

3. Start with container
```console
$ docker-compose run ubuntu-pyenv-tox bash
```

## Current usage
- pypika
- tortoise-orm
