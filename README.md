
# melange+apko learning

## melange command

* gen key

```code
docker run --rm -v "${PWD}":/work cgr.dev/chainguard/melange keygen
```

* package

```code
 docker run --rm --privileged -v "${PWD}":/work \
    cgr.dev/chainguard/melange build demo.yaml \
    --arch amd64 \
    --signing-key melange.rsa
```

## apko command

* build

```code
docker run --rm -v "${PWD}":/work \
    cgr.dev/chainguard/apko build --debug app-base.yaml \
    dalongdemoapp:v1  dalongdemoapp.tar -k melange.rsa.pub \
    --arch amd64
```
