ARG PGVERSION=11
FROM ghcr.io/tuskforce/postgres:${PGVERSION}
WORKDIR /usr/src/app

COPY . .
RUN make && \
    rm *

