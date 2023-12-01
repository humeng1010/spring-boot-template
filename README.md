# boot-template

> author: humeng
> 
> github: https://github.com/humeng1010

- SpringBoot——2.3.7.RELEASE
- spring-boot-starter-data-redis——
- commons-pool2——对象池，使用redis时必须引入
- redisson-spring-boot-starter——3.16.0
- mysql——8.0.22
- druid——1.1.23
- mybatis-plus-boot-starter——3.4.1
- minio——8.0.3
- fastjson——1.2.41
- guava——29.0-jre
- spring-boot-starter-data-elasticsearch——
- es——7.6.2
- spring-boot-starter-amqp——
- rabbitmq——3.9.5
- UserAgentUtils——1.20
- hutool——5.4.5
- jjwt——0.9.1
- xxl-job-core——2.1.0
- netty-socketio——1.7.16


## rabbitmq

本demo时，RabbitMQ 版本使用 `3.9.5`，使用 docker 运行，下面是所有步骤：

1. 下载镜像：`docker pull rabbitmq:3.9.5`
2. 运行容器：`docker run -d -p 5671:5617 -p 5672:5672 -p 4369:4369 -p 15671:15671 -p 15672:15672 -p 25672:25672 --name rabbit-3.9.5 rabbitmq:3.9.5`
3. 进入容器：`docker exec -it rabbit-3.9.5 /bin/bash`
4. 更新下载工具：`apt-get update`
5. 给容器安装 下载工具 wget：`apt-get install -y wget`
6. 下载插件包，因为我们的 `RabbitMQ` 版本为 `3.9.5` 所以我们安装 `3.9.x` 版本的延迟队列插件
    > https://github.com/rabbitmq/rabbitmq-delayed-message-exchange/releases/tag/3.9.0
   > https://github.com/rabbitmq/rabbitmq-delayed-message-exchange/releases/download/3.9.0/rabbitmq_delayed_message_exchange-3.9.0.ez
   ```bash
   root@a5c9e4cb1507:/# cd plugins
   root@f72ac937f2be:/plugins# wget https://github.com/rabbitmq/rabbitmq-delayed-message-exchange/releases/download/3.9.0/rabbitmq_delayed_message_exchange-3.9.0.ez
   ```
7. 启动延迟队列插件
   ```yaml
   /plugins# rabbitmq-plugins enable rabbitmq_delayed_message_exchange
   The following plugins have been configured:
     rabbitmq_delayed_message_exchange
     rabbitmq_management
     rabbitmq_management_agent
     rabbitmq_web_dispatch
   Applying plugin configuration to rabbit@f72ac937f2be...
   The following plugins have been enabled:
     rabbitmq_delayed_message_exchange

   started 1 plugins.
   ```
8. 退出容器：`exit`
9. 停止容器：`docker stop rabbit-3.7.7`
10. 启动容器：`docker start rabbit-3.7.7`

## mysql


## redis


## es

