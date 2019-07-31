# docker-stellar-core-alpine

Stellar Core image built on Alpine Linux. Just in case you're building your Stellar tool using Alpine as a source too.

To use it as build source for other container do:

```Dockerfile
ARG STELLAR_CORE_VERSION=v11.3.0
FROM astroband/docker-stellar-core-alpine:${STELLAR_CORE_VERSION} AS stellar-core

# On target container:
RUN apk add --no-cache libpq libstdc++ curl
COPY --from=stellar-core /usr/local/bin/stellar-core .
```

Check available tags on [Dockerhub](https://cloud.docker.com/repository/docker/astroband/docker-stellar-core-alpine/tags)