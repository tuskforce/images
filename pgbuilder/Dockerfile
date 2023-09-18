ARG PGVERSION=11
FROM ghcr.io/tuskforce/postgres:${PGVERSION}
ARG PGVERSION=11
WORKDIR /usr/src/app

COPY . .
RUN make && \
    rm *

