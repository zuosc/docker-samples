# docker-samples

A project with custom & ready-to-use Docker images.

## MySQL/MariaDB

1. __Alpine with periodic backup__: minimal _MariaDB_ server with a daily backup schedule | _reference guide_: [MySQL/MariaDB with scheduled backups running in Docker] @ Medium.

command demo:

```
docker run -d \
     --name=mysql-backup \
     --restart=always \
     -v /etc/localtime:/etc/localtime:ro \
     -v /path:/opt/mysql/backup \
     -e MYSQL_CONTAINER_NAME=127.0.0.1 \
     -e MYSQL_DATABASE=DATABASE \
     -e MYSQL_ROOT_PASSWORD=PASSWORD \
     -u root \
     mysql_auto_backup \
     crond -f -d 8
```


## Nginx

1. __Alpine with logs saved in custom paths__: minimal _Nginx_ server with `error.log` and `access.log` stored in custom paths.

1. __Alpine listening in custom port__: minimal _Nginx_ server listening on port `8080`.

[MySQL/MariaDB with scheduled backups running in Docker]: https://medium.com/@ricardolsmendes/mysql-mariadb-with-scheduled-backup-jobs-running-in-docker-1956e9892e78
