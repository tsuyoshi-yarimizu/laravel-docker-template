FROM mysql:8.0

ARG DB_NAME=""
ARG DB_USER=""
ARG DB_PASSWORD=""
ARG DB_ROOT_PASSWORD=""

ENV MYSQL_DATABASE=${DB_NAME} \
    MYSQL_USER=${DB_USER} \
    MYSQL_PASSWORD=${DB_PASSWORD} \
    MYSQL_ROOT_PASSWORD=${DB_ROOT_PASSWORD} \
    TZ=Asia/Tokyo

COPY ./my.cnf /etc/mysql/conf.d/my.cnf
RUN chmod 644 /etc/mysql/conf.d/my.cnf