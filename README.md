### docker compose up -d
```
version: '3'

services:
   mysql:
     image: mysql:8.0.20
     restart: always
     environment:
       MYSQL_ROOT_PASSWORD: wordpress
       MYSQL_DATABASE: wordpress
       MYSQL_USER: wordpress
       MYSQL_PASSWORD: wordpress

   wordpress:
     depends_on:
       - mysql
     image: wordpress:php7.4-apache
     ports:
       - "8000:80"
     restart: always
     environment:
       WORDPRESS_DB_HOST: mysql:3306
       WORDPRESS_DB_USER: wordpress
       WORDPRESS_DB_PASSWORD: wordpress
```

### https://tech-lab.sios.jp/archives/20051
### dockerfile -> イメージのビルド
### compose.yml -> コンテナの実行
