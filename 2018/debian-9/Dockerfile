FROM bitnami/minideb-extras:stretch-r163
LABEL maintainer "Bitnami <containers@bitnami.com>"

# Install required system packages and dependencies
RUN install_packages libbz2-1.0 libc6 libcomerr2 libcurl3 libexpat1 libffi6 libfreetype6 libgcc1 libgcrypt20 libgmp10 libgnutls30 libgpg-error0 libgssapi-krb5-2 libhogweed4 libicu57 libidn11 libidn2-0 libjpeg62-turbo libk5crypto3 libkeyutils1 libkrb5-3 libkrb5support0 libldap-2.4-2 liblzma5 libmcrypt4 libncurses5 libnettle6 libnghttp2-14 libp11-kit0 libpcre3 libpng16-16 libpq5 libpsl5 libreadline7 librtmp1 libsasl2-2 libsqlite3-0 libssh2-1 libssl1.0.2 libssl1.1 libstdc++6 libsybdb5 libtasn1-6 libtidy5 libtinfo5 libunistring0 libxml2 libxslt1.1 openssh-client zlib1g
RUN bitnami-pkg unpack apache-2.4.35-0 --checksum 1e352e2185137fcad60bb6fdf2961368f59a35e2c2cab4ee94c77152f1c37299
RUN bitnami-pkg unpack php-7.1.22-3 --checksum 41d3a6d69a8624958ed765d8b562b3c9e852880a8bf0bad01aa870f630f98909
RUN bitnami-pkg install mysql-client-10.1.36-0 --checksum e265f405c7707a49615c141ecf1e49aa0dc218d1d4660bbb51e94cfaa584c272
RUN bitnami-pkg install libphp-7.1.22-2 --checksum 17857e3e8c600de1c2217151059044330186ff2a3f0574b564519c40a8f4fdbb
RUN bitnami-pkg install git-2.19.1-0 --checksum 9b307ee5210ce00c75fb644ebb8caaaee5298acc64fa862aa12e7fbde9f9edb7
RUN bitnami-pkg unpack phabricator-2018.40.0-0 --checksum 64c9c034f90e0103404af24850dfbfb1e9395b55f0f7320c1094c7a6a12f160f

COPY rootfs /
ENV APACHE_HTTPS_PORT_NUMBER="443" \
    APACHE_HTTP_PORT_NUMBER="80" \
    BITNAMI_APP_NAME="phabricator" \
    BITNAMI_IMAGE_VERSION="2018.40.0-debian-9-r1" \
    MARIADB_HOST="mariadb" \
    MARIADB_PASSWORD="" \
    MARIADB_PORT_NUMBER="3306" \
    MARIADB_USER="root" \
    PATH="/opt/bitnami/apache/bin:/opt/bitnami/php/bin:/opt/bitnami/php/sbin:/opt/bitnami/mysql/bin:/opt/bitnami/git/bin:/opt/bitnami/arcanist/bin:/opt/bitnami/phabricator/bin:$PATH" \
    PHABRICATOR_ALTERNATE_FILE_DOMAIN="" \
    PHABRICATOR_EMAIL="user@example.com" \
    PHABRICATOR_FIRSTNAME="FirstName" \
    PHABRICATOR_HOST="127.0.0.1" \
    PHABRICATOR_LASTNAME="LastName" \
    PHABRICATOR_PASSWORD="bitnami1" \
    PHABRICATOR_USERNAME="user" \
    SMTP_HOST="" \
    SMTP_PASSWORD="" \
    SMTP_PORT="" \
    SMTP_PROTOCOL="" \
    SMTP_USER=""

EXPOSE 80 443

ENTRYPOINT [ "/app-entrypoint.sh" ]
CMD [ "/run.sh" ]
