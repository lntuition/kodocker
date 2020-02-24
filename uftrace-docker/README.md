# uftrace
Image for development [uftrace](https://github.com/namhyung/uftrace).

## How to use
1. Clone [kodocker](https://github.com/lntuition/kodocker) repository.
2. Add your uftrace folders into `uftrace` folder.
3. Build image
```console
$ docker-compose build
```

4. Start with container
```console
$ docker-compose up -d
$ docker-compose exec uftrace bash
```
