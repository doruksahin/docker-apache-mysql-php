# Boilerplate code for simple LAMP stack in Docker
## What is this?
This repository has some basic codes to help you kickstart hosting a PHP site with Apache and MySQL.
It could be used to transfer your existing PHP website to Docker.
## How to use it?
You need Docker and Docker Compose to be installed on your computer/server.
You can simply start the services with the `docker-compose up` command. It's suggested to do a first run without the `-d` attribute, to see all outputs from each containers to check for any configuration errors.
## Used images
- Apache: `ubuntu/apache2:2.4-20.04_beta`
- PHP: `php:7-fpm` (feel free to change it to your desired version. It should be PHP 8, not 7)
- MySQL: `mariadb` (Choose your desired version. By default it's the latest)
## Folder structure
- `conf`: All the configuration files mapped into this folder.
  - `apache`: Apache configuration files. By default only the sites-available directory is mounted.
    - `sites-available`: VirtualHosts, 000-default.conf is used for the config.
  - `php`: PHP configuration files, php.ini, etc.
  - `php-fpm`: The stack uses PHP-FPM, which can run multiple PHP instanced in pools. You can configure them here.
- `db`: Permanent storage for the MariaDB server
- `html`: The served files go there directly.
- `images`: Directory to store custom Docker images for the project.
- `log`: You can find there all the log files from the different containers.
