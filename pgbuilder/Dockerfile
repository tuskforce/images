FROM rockylinux:8
ARG PGVERSION=11
WORKDIR /usr/src/app

COPY . .
RUN dnf install -y make rpmdevtools rpm-build && \
    make && \
    rm *

