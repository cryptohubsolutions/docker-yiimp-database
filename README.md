# docker-yiimp-database
Dockerfile for Yiimp database frontend based on linux debian and tpruvot/yiimp original repository.

# Why not alpine ?
It seems that mysql doesn't currently build on alpine.

# Usage
```
docker pull jsminet/docker-yiimp-database
docker run -d -e MYSQL_ROOT_PASSWORD=secret -e MYSQL_DATABASE=yiimpfrontend -p 3306:3306 jsminet/docker-yiimp-database
```

You can use you own git repository by changing the ARG value at build time

```
git clone https://github.com/jsminet/docker-yiimp-database.git
docker build --build-arg REPOSITORY=https://github.com/YOUR_FORKED_REPOSITORY_NAME . -t IMAGE_NAME
```

# Use mariadb instead of mysql
```
docker pull jsminet/docker-yiimp-database:mariadb
docker run -d -e MYSQL_ROOT_PASSWORD=secret -e MYSQL_DATABASE=yiimpfrontend -p 3306:3306 jsminet/docker-yiimp-database:mariadb
```

# For informations
- SQL File 2016-04-03-yaamp.sql.gz is renamed to sql/0000-00-00-initial.sql.gz to be imported first
- init-db.sh is used to force the import as there are duplicated fields in imported sql files