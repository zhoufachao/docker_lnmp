## 简介

用 Docker 容器服务的方式搭建 php 环境，易于维护、升级。使用前需了解 Docker 的基本概念，常用基本命令。
可以一条条命令执行 docker 命令来构建镜像，容器。这里推荐使用 docker-compose 来管理，执行项目，下面是使用流程。

相关软件版本：

- PHP 8.0
- MySQL 8
- Nginx 1.12
- Redis 3.1.6

用到的 PHP 拓展

- redis 3.1.6

## 使用

### 1.安装 Docker，Docker-compose

- Docker，详见官方文档：https://docs.docker.com/
- docker-compose，文档：https://docs.docker.com/compose/install/

```
sudo pip install -U docker-compose
```

### 2.下载 php-docker

直接 clone：

```
git clone git@git.n.xiaomi.com:zhoufachao/docker_lnmp.git
```

或者下载 zip 压缩包也可以。

### 3.下载需要的拓展包

先下载好要使用的拓展包，如果编译出错要多次构建容器就可以省掉下载时间。

```
cd docker_lnmp/files

wget https://pecl.php.net/get/redis-3.1.6.tgz -O php/pkg/redis.tgz
```

### 4.docker-compose 构建项目

进入 docker-compose.yml 所在目录：
执行命令：

```
docker-compose up
```

如果没问题，下次启动时可以以守护模式启用，所有容器将后台运行：

```
docker-compose up -d
```

使用 docker-compose 基本上就这么简单，Docker 就跑起来了，用 stop，start 关闭开启容器服务。  
更多的是在于编写 dockerfile 和 docker-compose.yml 文件。

可以这样关闭容器并删除服务：

```
docker-compose down
```
