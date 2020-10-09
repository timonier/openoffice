FROM ubuntu:latest

LABEL \
    maintainer="Morgan AUCHEDE <morgan.auchede@gmail.com>"

ENV \
    LC_ALL=C.UTF-8 \
    NO_AT_BRIDGE=1

RUN set -e -u -x \
\
    # Prepare system
\
    && export DEBIAN_FRONTEND=noninteractive \
    && apt-get update \
\
    # Install packages
\
    && BUILD_DEPS="curl" \
    && apt-get install --no-install-recommends --yes ${BUILD_DEPS} ca-certificates default-jre libxt6 locales \
\
    # Install openoffice
\
    && curl --location "http://archive.apache.org/dist/openoffice/4.1.7/binaries/en-GB/Apache_OpenOffice_4.1.7_Linux_x86-64_install-deb_en-GB.tar.gz" | tar --directory /tmp --extract --gzip \
    && dpkg --install /tmp/en-GB/DEBS/*.deb \
    && dpkg --install /tmp/en-GB/DEBS/desktop-integration/*.deb \
\
    # Install unoconv
\
    && curl --location "https://github.com/dagwieers/unoconv/archive/0.9.0.tar.gz" | tar --directory /tmp --extract --gzip \
    && mv /tmp/unoconv-0.9.0 /opt/unoconv \
\
    # Clean
\
    && apt-get remove --purge --yes ${BUILD_DEPS} \
    && apt-get autoremove --purge --yes \
    && rm -f -r /tmp/* /var/lib/apt/lists/*

COPY rootfs/ /
