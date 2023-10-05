# Copyright (c) 2021 Intel Corporation
#
# SPDX-License-Identifier: Apache-2.0

FROM ubuntu:22.04
ENV DEBIAN_FRONTEND=noninteractive

ARG ARCH

# kernel deps
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
	    bc \
	    bison \
	    build-essential \
	    ca-certificates \
	    curl \
	    flex \
	    git \
	    iptables \
	    kmod \
	    libelf-dev \
	    libssl-dev \
	    gettext \
	    rsync \
	    cpio \
	    patch && \
    GCC_ARCH="${ARCH}" && if [ "${ARCH}" = "ppc64le" ]; then GCC_ARCH="powerpc64le"; fi && \
	if [ "${ARCH}" != "$(uname -m)" ]; then apt-get install --no-install-recommends -y gcc-"${GCC_ARCH}"-linux-gnu binutils-"${GCC_ARCH}"-linux-gnu; fi && \
    apt-get clean && apt-get autoclean && rm -rf /var/lib/apt/lists/*
