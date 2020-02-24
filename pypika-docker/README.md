# PyPika
Image for development [PyPika](https://github.com/kayak/pypika).
This image is based on Ubuntu and including `pyenv` and `tox`.

## How to use
1. Clone [kodocker](https://github.com/lntuition/kodocker) repository.
2. Add your pypika folders into `pypika` folder.
3. Customize args to control `pyenv` python version

|Argument name   |default      |
|----------------|-------------|
|PYTHON35_VERSION|3.5.9        |
|PYTHON36_VERSION|3.6.10       |
|PYTHON37_VERSION|3.7.6        |
|PYPY3_VERSION   |pypy3.6-7.3.0|

4. Build image
```console
$ docker-compose build
```

5. Start with container
```console
$ docker-compose up -d
$ docker-compose exec pypika bash
```
