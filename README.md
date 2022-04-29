# Docker Setup Files for Laravel

This is a really basic setup to get Docker running with Laravel.

## What will be installed?
- PHP 8.0
- Redis 6.2
- Node 18
- Composer
- MariaDB 10.7

## Steps
1. Copy all files and folders to the Laravel project folder
2. Copy below into .env, read comments and edit (all required)
```
# in docker-compose.yml line 71 (NETWORKS) change it to whatever is set for NETWORKS
# don't see a way to set it dynamically there
NETWORKS=

APP_USER=user
APP_CONTAINER_NAME=

# DB_HOST is already in Laravel's .env, make sure to update it to be db
# db is the docker service name for the database
# if it is not updated, the app cannot connect to the db
# DB_HOST=db
DB_CONTAINER_NAME=
DB_CONTAINER_PORT=

NGINX_CONTAINER_NAME=
NGINX_CONTAINER_PORT=

# REDIS_HOST needs to be the same as this variable in Laravel's .env
REDIS_CONTAINER_NAME=
REDIS_CONTAINER_PORT=

NPM_CONTAINER_NAME=
```
3. Edit the `.env` file, make sure to set `DB_HOST=db` and all `DB_`
4. Run `docker-compose up --build -d` to build the containers (`docker-compose up -d` only after container is built the first time)
5. Run `./php artisan key:generate --ansi`
6. Do things to get it started

## Commands
Since you won't have PHP,Node,NPM,Composer installed locally, these commands will be shortcuts to use them in Docker container
- PHP `./php <command>`
- NPM `./npm <command>`
- Composer `./composer <command>`
- Docker Build and Start `docker-compose up --build -d`
- Docker Start `docker-compose up -d`
- Docker Stop `docker-compose down`