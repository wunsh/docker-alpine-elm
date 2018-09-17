# Elm on Alpine with Docker

An easy way to start with Elm. No any system-wide dependencies except for Docker.

This is full working image of Elm language 0.19 and 0.18 built on top of Alpine.

Since the image is based on Alpine distributive, it's suitable for use at production servers as base image.


## Docker tags

You can choose one of the variants below:

- Elm 0.19 on Alpine 3.8: `latest`, `0.19`, `0.19-alpine3.8`;
- Elm 0.19 on Alpine 3.7: `0.19-alpine3.7`;
- Elm 0.18 on Alpine 3.8: `0.18`, `0.18-alpine3.8`;
- Elm 0.18 on Alpine 3.7: `0.18-alpine3.7`.

See [official repository](https://hub.docker.com/r/wunsh/alpine-elm/) at Docker Hub.

## Usage

There are `8000` port is exposed in Dockerfile and `/var/opt` directory is prepared for mounting.

### Elm 0.19

Check it out:

```bash
$ docker run wunsh/alpine-elm:latest
```

Now, try to play with Elm in the interactive REPL:

```bash
docker run -it wunsh/alpine-elm:latest repl
```

The more complicated way to play with Elm is using Reactor. This is on-the-fly development server, launched on `8000` port:

```bash
docker run $(pwd):/var/opt/ -p 8000:8000 -it wunsh/alpine-elm:latest reactor
```

You can start new project in the current directory like this:

```bash
docker run $(pwd):/var/opt/ -it wunsh/alpine-elm:latest init
```

Another commands supported by Elm 0.19:

```bash
elm make    --help
elm install --help
elm bump    --help
elm diff    --help
elm publish --help
```

### Elm 0.18

Approaches for 0.18 version are the same as presented above.
