FROM ubuntu:latest

LABEL \
    maintainer="Morgan Auchede <morgan.auchede@gmail.com>"

ENV \
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
    # Install dumb-entrypoint
\
    && curl --location "https://github.com/timonier/dumb-entrypoint/raw/master/src/dumb-entrypoint/installer" | bash -s -- install \
    && curl --location "https://github.com/timonier/dumb-entrypoint/raw/master/src/gosu/installer" | bash -s -- install \
\
    # Install openoffice
\
    && export $(curl --location "https://github.com/timonier/version-lister/raw/generated/_/openoffice/latest" | xargs) \
    && curl --location "${OPENOFFICE_PACKAGE}" | tar --directory /tmp --extract --gzip \
    && dpkg --install /tmp/"${OPENOFFICE_LANG}"/DEBS/*.deb \
    && dpkg --install /tmp/"${OPENOFFICE_LANG}"/DEBS/desktop-integration/*.deb \
\
    # Install unoconv
\
    && export $(curl --location "https://github.com/timonier/version-lister/raw/generated/dagwieers/unoconv/latest" | xargs) \
    && curl --location "${UNOCONV_SOURCE}" | tar --directory /tmp --extract --gzip \
    && mv /tmp/unoconv-"${UNOCONV_VERSION}" /opt/unoconv \
\
    # Clean
\
    && apt-get remove --purge --yes ${BUILD_DEPS} \
    && apt-get autoremove --purge --yes \
    && rm -f -r /tmp/* /var/lib/apt/lists/*

COPY rootfs/ /

ENTRYPOINT [ "dumb-entrypoint" ]
