# docker commands and install  

## 常用命令
```
systemctl start docker

docker ps -a

docker images

// 获取镜像配置
docker inspect <container_id>

// 进入容器
docker exec -it <container_id> bash

// 查看最近 10 行日志
docker logs -f -t --tail 10 <container_id>
```

## 一. [opengrok](https://hub.docker.com/r/opengrok/docker) 源码阅读环境搭建，如 [androidxref](http://androidxref.com/) 

### 1.install,[opengrok/docker](https://hub.docker.com/r/opengrok/docker)
```
docker pull opengrok/docker
```

### 2.启动，挂载源码目录，注意添加 `--privileged=true` 属性，

```
docker run -d -v <path/to/your/src>:/opengrok/src  --privileged=true -p 8080:8080 opengrok/docker:latest

```

### 3.默认 10 min 索引一次，可手动进行索引
```
docker exec <container_id> /scripts/index.sh

```
> 其他配置参考 [此处](https://hub.docker.com/r/opengrok/docker)。

