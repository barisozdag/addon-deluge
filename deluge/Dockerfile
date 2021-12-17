ARG BUILD_FROM=ghcr.io/hassio-addons/debian-base/aarch64:5.2.2
# hadolint ignore=DL3006
FROM ${BUILD_FROM}

# Set shell
SHELL ["/bin/bash", "-o", "pipefail", "-c"]

# Setup base system
ARG BUILD_ARCH=aarch64
# environment variables
ARG DEBIAN_FRONTEND="noninteractive"
ENV PYTHON_EGG_CACHE="/config/plugins/.python-eggs"

ARG RELEASE
RUN \
    apt-get update \
    && apt-get install -y --no-install-recommends \
        gnupg=2.2.27-2 \
    && apt-key adv --keyserver keyserver.ubuntu.com --recv-keys C5E6A5ED249AD24C \
    && echo "deb http://ppa.launchpad.net/deluge-team/stable/ubuntu hirsute main" >> \
        /etc/apt/sources.list.d/deluge.list \
    && echo "deb-src http://ppa.launchpad.net/deluge-team/stable/ubuntu hirsute main" >> \
        /etc/apt/sources.list.d/deluge.list \
    && apt-get update \
    && apt-get install -y --no-install-recommends \
        deluge-common=${RELEASE} \
        deluged=${RELEASE} \
        deluge-console=${RELEASE} \
        deluge-web=${RELEASE} \
    \
    && apt-get -y autoremove \
    && apt-get -y clean \
    \
    && rm -fr \
        /tmp/* \
        /var/{cache,log}/* \
        /var/lib/apt/lists/*

# Copy root filesystem
COPY rootfs /

# Build arguments
ARG BUILD_ARCH
ARG BUILD_DATE
ARG BUILD_DESCRIPTION
ARG BUILD_NAME
ARG BUILD_REF
ARG BUILD_REPOSITORY
ARG BUILD_VERSION

# Labels
LABEL \
    io.hass.name="${BUILD_NAME}" \
    io.hass.description="${BUILD_DESCRIPTION}" \
    io.hass.arch="${BUILD_ARCH}" \
    io.hass.type="addon" \
    io.hass.version=${BUILD_VERSION} \
    maintainer="Barış Özdağ" \
    org.opencontainers.image.title="${BUILD_NAME}" \
    org.opencontainers.image.description="${BUILD_DESCRIPTION}" \
    org.opencontainers.image.vendor="barisozdag's Personal Home Assistant Add-ons" \
    org.opencontainers.image.authors="Barış Özdağ" \
    org.opencontainers.image.licenses="MIT" \
    org.opencontainers.image.url="https://github.com/${BUILD_REPOSITORY}" \
    org.opencontainers.image.source="https://github.com/${BUILD_REPOSITORY}" \
    org.opencontainers.image.documentation="https://github.com/${BUILD_REPOSITORY}/blob/main/README.md" \
    org.opencontainers.image.created=${BUILD_DATE} \
    org.opencontainers.image.revision=${BUILD_REF} \
    org.opencontainers.image.version=${BUILD_VERSION}
