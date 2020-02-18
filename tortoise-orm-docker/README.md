# tortoise-orm
Image for development [tortoise-orm](https://github.com/tortoise/tortoise-orm).
This image is based on Ubuntu and including `pyenv` and `tox`.

## How to use
1. Clone [kodocker](https://github.com/lntuition/kodocker) repository.
2. Add your tortoise-orm folders into `tortoise-orm` folder.
3. Customize args to control `pyenv` python version

|Argument name   |default      |
|----------------|-------------|
|PYTHON36_VERSION|3.6.10       |
|PYTHON37_VERSION|3.7.6        |
|PYTHON38_VERSION|3.8.1        |
|PYPY3_VERSION   |pypy3.6-7.3.0|

4. Build image
```console
$ docker-compose build
```

5. Start with container
```console
$ docker-compose up -d
$ docker-compose exec tortoise-orm bash
```
