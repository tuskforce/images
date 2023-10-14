ARG PGVERSION=11
FROM ghcr.io/tuskforce/rhpg:${PGVERSION}
ARG PGVERSION=11
WORKDIR /usr/src/app

COPY . .
RUN echo PGV=${PGVERSION} && \
    make && \
    rm *

