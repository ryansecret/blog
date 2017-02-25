---
title: docker 常用命令
date: 2016-12-14 17:56:03
tags:
---
总结一下常用命令:

其中<>阔起来的参数为必选，[]阔起来为可选

docker version 查看docker的版本号，包括客户端、服务端、依赖的Go等
docker info 查看系统(docker)层面信息，包括管理的images, containers数等
docker search <image> 在docker index中搜索image
docker pull <image> 从docker registry server 中下拉image
docker push <image|repository> 推送一个image或repository到registry
docker push <image|repository>:TAG 同上，指定tag
docker inspect <image|container> 查看image或container的底层信息
docker images TODO filter out the intermediate image layers (intermediate image layers 是什么)
docker images -a 列出所有的images
docker ps 默认显示正在运行中的container
docker ps -l 显示最后一次创建的container，包括未运行的
docker ps -a 显示所有的container，包括未运行的
docker logs <container> 查看container的日志，也就是执行命令的一些输出
docker rm <container...> 删除一个或多个container
docker rm `docker ps -a -q` 删除所有的container
docker ps -a -q | xargs docker rm 同上, 删除所有的container
docker rmi <image...> 删除一个或多个image
docker start/stop/restart <container> 开启/停止/重启container
docker start -i <container> 启动一个container并进入交互模式
docker attach <container> attach一个运行中的container
docker run <image> <command> 使用image创建container并执行相应命令，然后停止
docker run -i -t <image> /bin/bash 使用image创建container并进入交互模式, login shell是/bin/bash
docker run -i -t -p <host_port:contain_port> 将container的端口映射到宿主机的端口
docker commit <container> [repo:tag] 将一个container固化为一个新的image，后面的repo:tag可选
docker build <path> 寻找path路径下名为的Dockerfile的配置文件，使用此配置生成新的image
docker build -t repo[:tag] 同上，可以指定repo和可选的tag
docker build - < <dockerfile> 使用指定的dockerfile配置文件，docker以stdin方式获取内容，使用此配置生成新的image
docker port <container> <container port> 查看本地哪个端口映射到container的指定端口，其实用docker ps 也可以看到


### 安装docker
1. 利用官方脚本：

```
$ sudo yum update
$ sudo curl -sSL https://get.docker.com/ | sh
```
2.  用黄狗安装：

```
$ sudo yum update
$ sudo yum -y install docker
$ sudo systemctl start docker
```
### 删除操作
##### 删除所有已经停止的continer  -q 列出所有id

```
docker rm $(docker ps -a -q)
```
##### 删除所有镜像

```
docker rmi $(docker images | grep none | awk '{print $3}' | sort -r)
```
### 命令说明
1. 其中go的语法模板
 
```
docker images --format "{{.ID}}: {{.Repository}}"
docker images --format "table {{.ID}}\t{{.Repository}}\t{{.Tag}}"
```
2. filter 过滤参数
 
```
docker images -f since=mongo:3.2
```
 表示自从3.2 版本以来所有的镜像。
3. docker run -it --rm --name ryanserver ubuntu:14.04 bash 
   
   it 表示交互终端 
   rm 推出后删除
   ubuntu  镜像名称
   bash bash命令
   naem 指定container名称
```
docker run --name webserver -d -p 85:80 nginx
```

4. docker commit [OPTIONS] CONTAINER [REPOSITORY[:TAG]]
- -a :提交的镜像作者；
- -c :使用Dockerfile指令来创建镜像；
- -m :提交时的说明文字；
- -p :在commit时，将容器暂停。
如：

```
$ docker commit \
    --author "Tao Wang <twang2218@gmail.com>" \
    --message "修改了默认网页" \
    webserver \
    nginx:v2
```
5.通过dockfile制作镜像

```
FROM nginx
RUN echo '<h1>Hello, Docker!</h1>' > /usr/share/nginx/html/index.html
```
from 指定基础镜像 

Dockerfile中每次运行run 都执行了一层。&& 将各个所需命令串联起来

Dockerfile 支持 Shell 类的行尾添加 \ 的命令换行方式，以及行首# 进行注释的格式
一定要确保每一层只添加真正需要添加的东西，任何无关的东西都应该清理掉。

copy 文件时可使用通配符，其通配符规则要满足 Go 的 filepath.Match 规则，如：

```
COPY hom* /mydir/
COPY hom?.txt /mydir/
```
Add 功能和copy 类似，不过自带解压功能：

```
FROM scratch
ADD ubuntu-xenial-core-cloudimg-amd64-root.tar.gz /
```
###### 环境变量的配置
格式有两种：
  ● ENV <key> <value>
  ● ENV <key1>=<value1> <key2>=<value2>...
例如 ENV VERSION=1.0 DEBUG=on \
     NAME="Happy Feet
######  匿名卷
在 Dockerfile 中，我们可以事先指定某些目录挂载为匿名卷，
任何向 /data 中写入的信息都不会记录进容器存储层，从而保证了容器存储层的无状态化。当然，运行时可以覆盖这个挂载设置。比如：
docker run -d -v mydata:/data xxxx
###### 挂载host目录
将host机中的文件挂载到container中：
docker可以支持把一个宿主机上的目录挂载到镜像里。

```
docker run -it -v /home/dock/Downloads:/usr/Downloads ubuntu64 /bin/bash
```

通过-v参数，冒号前为宿主机目录，必须为绝对路径，冒号后为镜像内挂载的路径。

一个dockfile:
 
```
MAINTAINER Anna Doe <anna@example.com>
nodejs pm2:
FROM node:0.11.13
# or just node, without tag

RUN npm install -g pm2
RUN pm2 dump
# dump will start pm2 daemon and create everything needed

VOLUME ["/srv/apps", "/srv/logs", "/srv/server.json"]
# don't put the files in docker container, user -v

EXPOSE 3000

CMD ["pm2", "start", "/srv/server.json", "--no-daemon"]
# no daemon mode for docker
```

6. docker build -t repo[:tag] . 
   
可以指定repo和可选的tag
如果注意，会看到 docker build 命令最后有一个 .。. 表示当前目录
copy命令只有在当前上下文有有效

7. 从container中导出
导出(Export)
Export命令用于持久化容器（不是镜像）
接着执行导出：
sudo docker export <CONTAINER ID> > /home/export.tar

导出后，可以通过docker import   导入，如

```
cat busy.tar | sudo docker import - busy:v1.0

```

8. 保存镜像
   sudo docker save busybox-1 > /home/save.tar


```
用户既可以使用 docker load 来导入镜像存储文件到本地镜像库，也可以使用 docker import 来导入一个容器快照到本地镜像库。这两者的区别在于容器快照文件将丢弃所有的历史记录和元数据信息（即仅保存容器当时的快照状态），而镜像存储文件将保存完整记录，体积也要大。此外，从容器快照文件导入时可以重新指定标签等元数据信息。
```

9. docker 自启动配置

自动启动container 如下：

```
docker run -ti --restart=on-failure:3   
失败后会启动三次
```
10. 用非root用户操作docker
下面是使用非root用户操作的步骤

```
创建docker组
sudo groupadd docker
将当前用户加入docker组
sudo gpasswd -a ${USER} docker
重新启动docker服务（下面是CentOS7的命令）
sudo systemctl restart docker
当前用户退出系统重新登陆
运行docker命令
docker ps
```

11.用docker 启动zookeeper 

```
ps -aux | grep docker
docker run  --name alizookeeper --restart always -d -P zookeeper
```

 