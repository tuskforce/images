FROM rockylinux:8
ARG PGVERSION=11
ENV PGVERSION=${PGVERSION}
ENV PGBIN=/usr/bin
ENV PGDATABASE=wdms
ENV PGDATA=/var/lib/pgsql/data
WORKDIR /usr/src/app

COPY . .
RUN dnf install -y make && \
    make && \
    rm *

