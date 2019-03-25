FROM alpine:3.7
MAINTAINER Karmashkin <vlad@zolotous.com>

RUN apk upgrade -U \
    && apk --update add nginx \
                        tzdata \
    && rm -rf /var/cache/apk/*

RUN chown -R nginx:www-data /var/lib/nginx

COPY nginx.conf  /etc/nginx/nginx.conf

RUN mkdir /www
VOLUME /www

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
