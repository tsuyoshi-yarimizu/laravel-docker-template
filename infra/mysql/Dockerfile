FROM mysql:8.0

ARG DB_NAME="laravel_local"
ARG DB_USER="laravel"
ARG DB_PASSWORD="secret"
ARG DB_ROOT_PASSWORD="secret"

ENV MYSQL_DATABASE=${DB_NAME} \
    MYSQL_USER=${DB_USER} \
    MYSQL_PASSWORD=${DB_PASSWORD} \
    MYSQL_ROOT_PASSWORD=${DB_ROOT_PASSWORD} \
    TZ=Asia/Tokyo

COPY ./my.cnf /etc/mysql/conf.d/my.cnf
RUN chmod 644 /etc/mysql/conf.d/my.cnf