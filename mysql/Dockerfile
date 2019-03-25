FROM alpine:3.7
MAINTAINER Naerymdan <vincent.dev@gmail.com>

RUN addgroup -S mysql && adduser -S -g mysql mysql

RUN apk upgrade -U \
    && apk --update add \
    mysql \
    mysql-client \
    tzdata bash \
    && rm -rf /var/cache/apk/* \
    && rm -rf /var/lib/mysql

RUN mkdir /docker-entrypoint-initdb.d \
    && mkdir /var/lib/mysql \
    && mkdir /run/mysqld

COPY custom.cnf              /etc/mysql/my.cnf
COPY docker-entrypoint.sh    /

RUN chmod 644 /etc/mysql/my.cnf \
    && chmod +x /docker-entrypoint.sh \
    && sed -Ei 's/^(bind-address|log)/#&/' /etc/mysql/my.cnf

VOLUME /var/lib/mysql

EXPOSE 3306

ENTRYPOINT ["/docker-entrypoint.sh"]

CMD ["mysqld"]
