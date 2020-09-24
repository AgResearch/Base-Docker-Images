FROM postgres:9.5

ARG BUILD_DATE
ARG VERSION
ENV VERSION ${VERSION:-1.1.4}

LABEL org.label-schema.build-date=$BUILD_DATE \
      org.label-schema.name="The SNP Pit Database" \
      org.label-schema.description="A database system to efficiently process and manage very large amounts of SNP data" \
      org.label-schema.url="https://thesnppit.net/" \
      org.label-schema.vendor="AgReserch Ltd" \
      org.label-schema.version=$VERSION \
      org.label-schema.schema-version="1.0"

LABEL maintainer="dan.sun@agresearch.co.nz"

RUN apt-get update \
 && apt-get install -y --no-install-recommends \
    wget \
    sudo

USER root

RUN wget --no-check-certificate https://tsp-repo.thesnppit.net/download/TheSNPpit-latest.tar.gz -O /usr/local/TheSNPpit-latest.tar.gz \
 && cd /usr/local \
 && tar xzvf TheSNPpit-latest.tar.gz \
 && rm TheSNPpit-latest.tar.gz \
 && cd /usr/local/TheSNPpit-1.1.4 \
 && sed -i.bak "s/ETC_DIR=.*/ETC_DIR=\$PG_DATA/" bin/INSTALL



