# Docker Setup Files for Laravel

This is a really basic setup to get Docker running with Laravel.

Scripts used are mainly run on Mac

## What will be installed?
- PHP 8.0
- Redis 6.2
- Node 18
- Composer
- MariaDB 10.7

## Steps
1. Copy all files and folders to the Laravel project folder except `.gitignore`
2. Edit `init` and fill out the variables from line 4 to 19
3. Run `./init`, this will automatically make a copy of `.env.example` to `.env` if it doesn't exist and updates `docker-compose.yml` and `.env`
4. Finish configuring `.env`
5. Run `docker-compose up --build -d` to build the containers (`docker-compose up -d` only after container is built the first time)
6. Run `./php artisan key:generate --ansi`
7. Code!

## Commands
Since you won't have PHP,Node,NPM,Composer installed locally, these commands will be shortcuts to use them in Docker container
- PHP `./php <command>`
- NPM `./npm <command>`
- Composer `./composer <command>`
- Docker Build and Start `docker-compose up --build -d`
- Docker Start `docker-compose up -d`
- Docker Stop `docker-compose down`