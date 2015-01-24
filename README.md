docker-symfony2
==================
This is the base image preconfigured with Ubuntu, Nginx, PHP-FPM to use with Symfony2 framework. It's based on another Docker image [olegpuzanov/docker-nginx-php5-fpm](https://github.com/olegpuzanov/docker-nginx-php5-fpm). Docker repository available here [olegpuzanov/docker-symfony2/](https://registry.hub.docker.com/u/olegpuzanov/docker-symfony2/).

**Modifications:**
- composer installed
- security fix for nginx + php-fpm applied: cgi.fix_pathinfo=0
- `date.timezone` set in `php.ini` as recommended by Symfony

**Build**

	docker build -t "olegpuzanov/symfony2" .

**Run**

	docker run -t -i -p 8080:80 -v /path/to/symfony:/var/www/ "olegpuzanov/symfony2" /bin/bash

**Launch**

	http://localhost:8080/web/app_dev.php

Note, if you have used the boot2docker virtual machine, you'll need to get the IP of the virtual host instead of using localhost. You can do this by running the following command `boot2docker ip`.