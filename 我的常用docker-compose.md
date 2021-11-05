# 我的常用docker-compose

![docker](https://qncdn.laufan.cn/img/20210627182125.jpg?imageView2/0/q/75%7Cimageslim)

为了方便以后使用，备份备查

变量名解释

> - 文件夹映射
>
>   volumes	主机文件夹:docker文件夹

> - 端口映射
>
>   ports		主机端口：docker端口

## Mysql

```yml
version: '3'
services:
  db:
    image: mysql:latest
    container_name: 'mysql'
    restart: always
    command: '--default-authentication-plugin=mysql_native_password'
    volumes:
      - ~/docker/mysql/db_data:/var/lib/mysql
    environment:
      - MYSQL_ROOT_PASSWORD=root
    ports:
      - 3306:3306
```

## Redis

```yml
version: '3'
services:
  redis:
    image: redis:alpine
    container_name: 'redis'
    restart: always
    ports:
        - 6379:6379
    volumes:
        - ~/docker/redis/data:/data
```

## RabbitMQ

```yml
version: "3"
services:
  rabbitmq:
    image: rabbitmq:3-management-alpine
    container_name: 'rabbitmq'
    restart: always
    ports:
        - 5672:5672
        - 15672:15672
    volumes:
        - ~/docker/rabbitmq/data/:/var/lib/rabbitmq/
        - ~/docker/rabbitmq/log/:/var/log/rabbitmq
```



