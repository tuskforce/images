FROM rockylinux:8
ARG PGVERSION=11
ENV PGVERSION=${PGVERSION}
ENV PGBIN=/usr/pgsql-${PGVERSION}/bin
ENV PGDATABASE=wdms
ENV PGDATA=/var/lib/pgsql/${PGVERSION}/data
WORKDIR /usr/src/app

COPY . .
RUN dnf install -y make && \
    make && \
    rm *

