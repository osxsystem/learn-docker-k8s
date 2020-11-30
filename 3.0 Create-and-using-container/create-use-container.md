# Create and using container

### Content

- Docker CLI and Engine
- Create a web server (Nginx) container
- How container manage commands
- Docker NETWORK basic

```shell
    $ docker version
    $ docker info
    $ docker <command> (options)
    $ docker <command> <sub-command> (options)
```
###

### Create a web server Nginx

```shell
    $ docker container run --publish 80:80 nginx
    $ docker container run --publish 80:80 --detach nginx
```

### Example:
```shell
    $ docker container run --publish 80:80 --detach --name webhost nginx
    $ docker container ls -a
    $ docker container logs webhost
    $ docker container top webhost
    $ docker container rm c4d c29 089
    $ docker container rm -f part_id
```

### Container vs VM

```shell
    $ docker run --name mongo -d mongo
    $ ps aux | grep mongo
```

### Assignment: manage multiple containers

- Run nginx, mysql, httpd (apache) server
- Run with `--detach` or `-d` and name them `--name`
- Nginx listen on port `80:80` httpd on port `8080:80`, mysql on `3306:3306`

* Hint: when running mysql, use the `--env` option or `-e` to pass in `MYSQL_RANDOM_ROOT_PASSWORD=yes`

```shell

    $ docker container run -d -p 3306:3306 --env MYSQL_RANDOM_ROOT_PASSWORD=yes --name mysql mysql

    $ docker container logs mysql

    $ docker container run -d --name webserver -p 8080:80 httpd
```

### Getting a bash shell inside an Container (mysql)

```shell
    $ docker container run -it 
```

