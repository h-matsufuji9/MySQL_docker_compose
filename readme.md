# Setting
## MySQL_docker_compose/docker-compose.yml
- MYSQL_ROOT_PASSWORD
- MYSQL_DATABASE
- MYSQL_USER
- MYSQL_PASSWORD

- volumes
    - Docker volume
        - mysql_data:/var/lib/mysql
    - HostDir
        - ./docker/db/data:/var/lib/mysql

## MySQL_docker_compose/docker/db/sql/init-database.sh
- -u
    - MYSQL_USER
- -p
    - MYSQL_PASSWORD
- dbname
    - MYSQL_DATABASE

# docker起動
docker-compose up -d

# docker停止
docker-compose stop

# volume削除
docker-compose down -v

# DB初期化(シェル実行)
./init-mysql.sh

# phpMyAdminで確認
http://localhost:8080