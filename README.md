# docker-dlib

Docker image with compiled Dlib

[![](https://images.microbadger.com/badges/version/m03geek/dlib:alpine.svg)](https://microbadger.com/images/m03geek/dlib:alpine "version")[![](https://images.microbadger.com/badges/image/m03geek/dlib:alpine.svg)](https://microbadger.com/images/m03geek/dlib:alpine "layers")

[![](https://images.microbadger.com/badges/version/m03geek/dlib:stretch.svg)](https://microbadger.com/images/m03geek/dlib:stretch "version")[![](https://images.microbadger.com/badges/image/m03geek/dlib:stretch.svg)](https://microbadger.com/images/m03geek/dlib:stretch "layers")

# Versions (latest)

* dlib - 19.8

# Dlib

Dlib is built from source. Latest git tag corresponds Dlib version.

## Compile options

```
-D CMAKE_BUILD_TYPE=RELEASE
-D CMAKE_INSTALL_PREFIX=$LIB_PREFIX
-D DLIB_NO_GUI_SUPPORT=OFF
-D DLIB_USE_BLAS=ON
-D DLIB_GIF_SUPPORT=ON
-D DLIB_PNG_SUPPORT=ON
-D DLIB_JPEG_SUPPORT=ON
-D DLIB_USE_CUDA=OFF"
```

## Image support

* png
* jpeg
* gif

# FFmpeg support

In order to add ffmpeg support just simply install it through package manager

## Alpine

```Dockerfile
RUN apk add -u --no-cache ffmpeg
# optioanlly export ffmpeg binaries to env (e.g. for fluent-ffmpeg module)
ENV FFMPEG_PATH='/usr/bin/ffmpeg' \
    FFPROBE_PATH='/usr/bin/ffprobe'
```

## Stretch

You may install ffmpeg from official repo, but I'd recommend deb-multimedia.

```Dockerfile
RUN echo "deb http://www.deb-multimedia.org stretch main non-free" >> "/etc/apt/sources.list" \
    && apt-get update && apt-get install -y deb-multimedia-keyring ffmpeg --no-install-recommends --allow-unauthenticated
# optioanlly export ffmpeg binaries to env (e.g. for fluent-ffmpeg module)
ENV FFMPEG_PATH='/usr/bin/ffmpeg' \
    FFPROBE_PATH='/usr/bin/ffprobe'
```

# Other images:

## Without FFmpeg

| OpenCV | Dlib | OpenCV+Dlib | OpenCV+Dlib+Node.js | OpenCV+Node.js | Dlib+Node.js |
|-|-|-|-|-|-|
| [Docker](https://hub.docker.com/r/m03geek/opencv/) | [Docker](https://hub.docker.com/r/m03geek/dlib/) | [Docker](https://hub.docker.com/r/m03geek/opencv-dlib/) | [Docker](https://hub.docker.com/r/m03geek/opencv-dlib-node/) | [Docker](https://hub.docker.com/r/m03geek/opencv-node/) | [Docker](https://hub.docker.com/r/m03geek/dlib-node/) |
| [Github](https://github.com/SkeLLLa/docker-opencv) | [Github](https://github.com/SkeLLLa/docker-dlib) | [Github](https://github.com/SkeLLLa/docker-opencv-dlib) | [Github](https://github.com/SkeLLLa/docker-opencv-dlib-node) | [Github](https://github.com/SkeLLLa/docker-opencv-node) | [Github](https://github.com/SkeLLLa/docker-dlib-node) |

## With FFmpeg

| OpenCV | OpenCV+Dlib | OpenCV+Dlib+Node.js | OpenCV+Node.js |
|-|-|-|-|
| [Docker](https://hub.docker.com/r/m03geek/ffmpeg-opencv/) | [Docker](https://hub.docker.com/r/m03geek/ffmpeg-opencv-dlib/) | [Docker](https://hub.docker.com/r/m03geek/ffmpeg-opencv-dlib-node/) | [Docker](https://hub.docker.com/r/m03geek/ffmpeg-opencv-dlib-node/) |
| [Github](https://github.com/SkeLLLa/docker-ffmpeg-opencv) | [Github](https://github.com/SkeLLLa/docker-ffmpeg-opencv) | [Github](https://github.com/SkeLLLa/docker-ffmpeg-opencv-dlib-node) | [Github](https://github.com/SkeLLLa/docker-ffmpeg-opencv-node) |