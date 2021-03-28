FROM nginx:1.15.12-alpine

LABEL maintainer="James Todd <toddwebnet@gmail.com>"

COPY nginx.conf /etc/nginx/

RUN apk update \
    && apk upgrade \
    && apk add --no-cache openssl \
    && apk add --no-cache bash \
    && adduser -D -H -u 1000 -s /bin/bash www-data

# ARG PHP_UPSTREAM_CONTAINER=php-fpm
# ARG PHP_UPSTREAM_PORT=9000


COPY docker-entrypoint.sh /usr/local/bin/
RUN chmod 777 /usr/local/bin/docker-entrypoint.sh
RUN ln -sf usr/local/bin/docker-entrypoint.sh /entrypoint.sh # backwards compat

ENTRYPOINT ["docker-entrypoint.sh"]

CMD ["nginx", "-g", "daemon off;"]


EXPOSE 80 443
