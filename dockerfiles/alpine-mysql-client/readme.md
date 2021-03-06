![docker](https://github.frapsoft.com/top/docker-security.jpg)

# alpine-mysql-client

[![Docker Automated Build](https://img.shields.io/docker/automated/ellerbrock/alpine-mysql-client.svg)](https://hub.docker.com/r/ellerbrock/alpine-mysql-client/) [![Docker Pulls](https://img.shields.io/docker/pulls/ellerbrock/alpine-mysql-client.svg)](https://hub.docker.com/r/ellerbrock/alpine-mysql-client/) [![Open Source Love](https://badges.frapsoft.com/os/v1/open-source.svg)](https://github.com/ellerbrock/open-source-badges/) [![Gitter Chat](https://badges.gitter.im/frapsoft/frapsoft.svg)](https://gitter.im/frapsoft/frapsoft/)

- Docker: [ellerbrock/alpine-mysql-client](https://hub.docker.com/r/ellerbrock/alpine-mysql-client/)

## Installation

`docker pull ellerbrock/alpine-mysql-client`


## About the Container

Base image is [Alpine Linux](https://alpinelinux.org/) which is a lightweight Distribution with a small surface area for security concerns, but with enough functionality for development and interactive debugging.  

To prevent zombie reaping i run [dumb-init](https://github.com/Yelp/dumb-init) as PID 1 which forwards signals to all processes running in the container. 

To increase security the container runs as a unprivileged User.  
In case you need to run for some reason stuff as root you can do this via `docker run -it -u root ellerbrock/alpine-mysql-client ...`.


## Configuration Parameter

_These Settings are **optional**, if not set the default values will be used._

```
# Optional Configuration Parameter
ARG SYSTEM_TZ
ARG SERVICE_USER
ARG SERVICE_HOME

# Default Settings
ENV SYSTEM_TZ ${SYSTEM_TZ:-Europe/Berlin}
ENV SERVICE_USER ${SERVICE_USER:-mysql}
ENV SERVICE_HOME ${SERVICE_HOME:-/home/${SERVICE_USER}}

```

### Dockerfile example:

```
docker build \
  --build-arg SYSTEM_TZ=Europe/Berlin \
  -t ellerbrock/alpine-mysql-client:latest .
```
Documentation: <https://docs.docker.com/engine/reference/builder/#/arg>

### docker-compose example: 

```
  args:
    SYSTEM_TZ: Europe/Berlin
    ...
```

Documentation: <https://docs.docker.com/compose/compose-file/#/args>

### Contact / Social Media

_Get the latest News about Web Development, Open Source, Tooling, Server & Security_

[![Github](https://github.frapsoft.com/social/github.png)](https://github.com/ellerbrock/)[![Docker](https://github.frapsoft.com/social/docker.png)](https://hub.docker.com/u/ellerbrock/)[![npm](https://github.frapsoft.com/social/npm.png)](https://www.npmjs.com/~ellerbrock)[![Twitter](https://github.frapsoft.com/social/twitter.png)](https://twitter.com/frapsoft/)[![Facebook](https://github.frapsoft.com/social/facebook.png)](https://www.facebook.com/frapsoft/)[![Google+](https://github.frapsoft.com/social/google-plus.png)](https://plus.google.com/116540931335841862774)[![Gitter](https://github.frapsoft.com/social/gitter.png)](https://gitter.im/frapsoft/frapsoft/)
