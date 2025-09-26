ARG PGVERSION=11
FROM ghcr.io/tuskforce/pg:${PGVERSION}
ARG PGVERSION=11
WORKDIR /usr/src/app

COPY . .
RUN echo PGV=${PGVERSION} && \
    make && \
    rm *

