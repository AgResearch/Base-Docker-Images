FROM agresearch/shiny:3.6.3

RUN apt-get update -qq && apt-get -y --no-install-recommends install \
  libxml2-dev \
  libcairo2-dev \
  libsqlite3-dev \
  libmariadbd-dev \
  libmariadbclient-dev \
  libpq-dev \
  libssl-dev \
  libcurl4-openssl-dev \
  libssh2-1-dev \
  unixodbc-dev

RUN install2.r --error \
    --deps TRUE \
    xml2 \
    tidyverse \
    devtools \
    formatR \
    remotes \
    caTools \
    dplyr \
    && rm -rf /tmp/downloaded_packages
  
RUN install2.r \
    --deps TRUE \
  	BiocManager \
    selectr \
    && rm -rf /tmp/downloaded_packages
