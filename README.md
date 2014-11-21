**Description**  

根据 [https://github.com/maxexcloo/Docker](https://github.com/maxexcloo/Docker "") 进行了优化，比如/data目录结构，使用一个/data目录作为所有Container的持久化数据目录，结构清晰。更换debian下载源，使用国内的163，速度更快。

精力问题，精简了一些服务和应用，需要了解更详细的青参考 [https://github.com/maxexcloo/Docker](https://github.com/maxexcloo/Docker "")

**Directory Structure**  

- **Nginx**

    Nginx based frameworks have a simple directory structure that can be used to easily deploy web applications using a volume on /data.

        /data
            /config
                /nginx 
                    *.conf // included by nginx
                /php5
                    *.conf // included by php-fpm
            /nginx/www
                    index.html // root web directory (index file is index.html or index.php)
            /log
                /nginx
                    error.log // nginx log file
                /php5
                    php-fpm.log // php-fpm log file
            /run
                filename.ext // private files such as passwords or keys

**Instructions**  
Instructions will be here when I get around to writing them!

**Usage**  
The following commands can be used to deploy some of the services offered by the Docker containers in this repository.

- **Applications**

    - **Adminer**

            docker run --env=[VIRTUAL_HOST=adminer.example.com] --link=[mariadb:mariadb, postgresql:postgresql] --name="adminer" -d rujews/adminer


    - **phpMyAdmin**

            docker run --name="phpmyadmin" -d --link mariadb:mariadb --env=VIRTUAL_HOST=phpmyadmin.example.com rujews/phpmyadmin

    - **Wordpress**

            docker run --name="wordpress-data" rujews/data
            docker run --name="wordpress" -it --link mariadb:mariadb --volumes-from="wordpress-data" --env=VIRTUAL_HOST=wordpress.example.com rujews/wordpress

- **Base**

    - **Data**

            docker run --name="data" -it rujews/data /bin/sh

    - **Debian**

            docker run --name="debian" -it rujews/debian /bin/bash

    - **Ubuntu**

            docker run --name="ubuntu" -it rujews/ubuntu /bin/bash

- **Frameworks**

    - **Nginx**

            docker run --name="nginx-data" rujews/data
            docker run --name="nginx" -it --volumes-from="nginx-data" --env=VIRTUAL_HOST=example.com,www.example.com rujews/nginx

    - **Nginx + PHP-FPM**

            docker run --name="nginx-php-data" rujews/data
            docker run --name="nginx-php" -it --volumes-from="nginx-php-data" --env=VIRTUAL_HOST=example.com,www.example.com rujews/nginx-php

- **Services**

    - **MariaDB**

            docker run --name="mariadb-data" rujews/data
            docker run --name="mariadb" -it --volumes-from="mariadb-data" rujews/mariadb

**Testing**  

