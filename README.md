# docker-codeigniter-apache 🐳

![License](https://img.shields.io/github/license/kenjis/docker-codeigniter-apache?color=f05340)
![Stars](https://img.shields.io/github/stars/kenjis/docker-codeigniter-apache?color=f05340)
![Issues](https://img.shields.io/github/issues/kenjis/docker-codeigniter-apache?color=f05340)
![Forks](https://img.shields.io/github/forks/kenjis/docker-codeigniter-apache?color=f05340)

## Introduction

Build a simple CodeIgniter development environment with docker-compose.
CodeIgniter version of [docker-laravel-apache](https://github.com/ucan-lab/docker-laravel-apache).

## Usage

```bash
$ git clone git@github.com:kenjis/docker-codeigniter-apache.git
$ cd docker-codeigniter-apache
$ make create-project # Install the latest CodeIgniter4 project
$ make install-recommend-packages # Not required
```

http://localhost

Read this [Makefile](https://github.com/kenjis/docker-codeigniter-apache/blob/master/Makefile).

## Container structure

```bash
├── web
├── db
└── phpmyadmin
```

### web container

- Base image
  - [php](https://hub.docker.com/_/php): 7.4-apache-buster
  - [composer](https://hub.docker.com/_/composer): 2.0
  - [node](https://hub.docker.com/_/node): node:14-buster

### db container

- Base image
  - [mysql](https://hub.docker.com/_/mysql): 8.0

### phpmyadmin container

- Base image
  - [phpmyadmin/phpmyadmin](https://hub.docker.com/r/phpmyadmin/phpmyadmin): 5.0.4

#### Persistent MySQL Storage

By default, the [named volume](https://github.com/compose-spec/compose-spec/blob/master/spec.md#volumes) is mounted, so MySQL data remains even if the container is destroyed.
If you want to delete MySQL data intentionally, execute the following command.

```bash
$ docker-compose down -v && docker-compose up
```
