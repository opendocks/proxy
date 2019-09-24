FROM jwilder/nginx-proxy

#
#--------------------------------------------------------------------------
# Software's Installation
#--------------------------------------------------------------------------
#
# Installing tools and PHP extentions using "apt", "docker-php", "pecl",
#
RUN apt-get update && \
    apt-get upgrade -yqq

ARG DEVELOPMENT_MODE=false

RUN if [ ${DEVELOPMENT_MODE} = true ]; then \
    # Install vim editor
    apt-get install -yqq --no-install-recommends\
    vim
;fi

# Clean up
RUN apt-get clean && \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* && \
    rm /var/log/lastlog /var/log/faillog
