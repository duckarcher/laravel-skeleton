# Laravel skeleton

This is the minimum setup needed for creating or cloning a laravel application.

# Support

This has been tested on a fresh Laravel 11 application.

# Quick setup

Inside the `laravel-skeleton` folder, run
```bash
docker compose up -d
```
to spin up the containers (php, nginx, mariadb).

Run
```bash
docker compose exec -it laravel-php bash
```
to get a shell inside the php container.

Then, run
```bash
composer create-project laravel/laravel .
```
to create the latest laravel application skeleton.

Now you can visit `http://127.0.0.1:1234/` to visit your laravel app.