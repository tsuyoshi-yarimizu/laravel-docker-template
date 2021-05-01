# laravel-docker-template

## Usage

### 1. Clone this template.

```
$ git clone git@github.com:tsuyoshi-yarimizu/laravel-docker-template.git YOUR_PROJECT_NAME

# make directory for application.
$ cd YOUR_PROJECT_NAME
$ mkdir src
```

### 2. up & build

```
$ cd YOUR_PROJECT_NAME
$ docker-compose up -d --build
```

### Laravel install

#### New application.

```
# new application.
$ docker-compose exec app bash
/work# composer create-project --prefer-dist "laravel/laravel=8.*" .
```

#### Exist application.

```
$ cd YOUR_PROJECT_NAME/src
$ git clone EXIST_APPLICATION_REPOSITORY .
```

## Settings

### Mysql

Change mysql conf `infra/mysql/Dockerfile` and `LARAVEL_APP/.env`.

.env

```.env
DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=laravel // infra/mysql/Dockerfile ARG DB_NAME
DB_USERNAME=root // infra/mysql/Dockerfile ARG DB_USER
DB_PASSWORD=secret // infra/mysql/Dockerfile ARG MYSQL_PASSWORD
```

