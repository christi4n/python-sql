# Sample Docker Compose file with MariaDB for MySQL, PHPmyAdmin UI and Python

## How-to

1) Check that the ports 6033 and 8081 are not alread used otherwise, change the ports in the docker compose file

    $ docker ps

2) Start with:

    $ docker-compose up -d

3) Head to the main UI, go to http://localhost:8081/

4) Login with the credentials provided in the docker-compose.yml file

5) Import DB with the CLI

    $ docker exec -i container_id /usr/bin/mysql -utest -ptest -hdb mydatabase < /path/to/my/file

There is a sql file in the init directory. The first time the container is created, it has access to these directory. This way, you can add multiple files and they will be executed following their name for the order. 

## Credits

Author: Christian BELLET