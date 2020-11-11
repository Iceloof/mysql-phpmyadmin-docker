# mysql-phpmyadmin-docker
Configure `docker-compose.yml` with your own setting

## Mysql
```
  container_name: <docker-name>
  image: mysql:latest
  restart: always
  environment:
    MYSQL_ROOT_PASSWORD: <ROOT PASSWORD>
  volumes:
    - <local path for data store>:/var/lib/mysql
  ports:
    - "<forward port>:3306"
```
## Phpmyadmin
```
  container_name: <docker-name>
  image: phpmyadmin/phpmyadmin:latest
  restart: always
  environment:
    PMA_HOST: <docker-db-name>
  ports:
    - "<forward port>:80"
```
## Build and run
```
docker-compose -f docker-compose.yml up -d
```