

# Docker

**Docker官方文档地址：[Docker Documentation ](https://docs.docker.com/)**

### 1、概述

##### **一、基本介绍**

Docker 是一个开源的应用容器引擎，基于 Go 语言 并遵从 Apache2.0 协议开源。

Docker 可以让开发者打包他们的应用以及依赖包到一个轻量级、可移植的容器中，然后发布到任何流行的 Linux 机器上，也可以实现虚拟化。

容器是完全使用沙箱机制，相互之间不会有任何接口（类似 iPhone 的 app）,更重要的是容器性能开销极低。

##### **二、应用场景**

Web 应用的自动化打包和发布。

自动化测试和持续集成、发布。

在服务型环境中部署和调整数据库或其他的后台应用。

从头编译或者扩展现有的 OpenShift 或 Cloud Foundry 平台来搭建自己的 PaaS 环境。

##### **三、Docker 的优势**

Docker 是一个用于开发，交付和运行应用程序的开放平台。Docker 使您能够将应用程序与基础架构分开，从而可以快速交付软件。借助 Docker，您可以与管理应用程序相同的方式来管理基础架构。通过利用 Docker 的方法来快速交付，测试和部署代码，您可以大大减少编写代码和在生产环境中运行代码之间的延迟。

1. 快速，一致地交付您的应用程序。Docker 允许开发人员使用您提供的应用程序或服务的本地容器在标准化环境中工作，从而简化了开发的生命周期。

   容器非常适合持续集成和持续交付（CI / CD）工作流程，请考虑以下示例方案：

   您的开发人员在本地编写代码，并使用 Docker 容器与同事共享他们的工作。
   他们使用 Docker 将其应用程序推送到测试环境中，并执行自动或手动测试。
   当开发人员发现错误时，他们可以在开发环境中对其进行修复，然后将其重新部署到测试环境中，以进行测试和验证。
   测试完成后，将修补程序推送给生产环境，就像将更新的镜像推送到生产环境一样简单。

2. 响应式部署和扩展
   Docker 是基于容器的平台，允许高度可移植的工作负载。Docker 容器可以在开发人员的本机上，数据中心的物理或虚拟机上，云服务上或混合环境中运行。Docker 的可移植性和轻量级的特性，还可以使您轻松地完成动态管理的工作负担，并根据业务需求指示，实时扩展或拆除应用程序和服务。

3. 在同一硬件上运行更多工作负载
   Docker 轻巧快速。它为基于虚拟机管理程序的虚拟机提供了可行、经济、高效的替代方案，因此您可以利用更多的计算能力来实现业务目标。Docker 非常适合于高密度环境以及中小型部署，而您可以用更少的资源做更多的事情。

### 2、虚拟化技术和容器化技术（虚拟机与容器）

**虚拟化技术特点**：1.资源占用多 2.冗余步骤多 3.启动很慢

**容器化技术**：容器化技术不是模拟的一个完整的操作系统

比较Docker和虚拟机的不同：

1. 传统虚拟机，虚拟出硬件，运行一个完整的操作系统，然后在这个系统上安装和运行软件。
2. Docker容器内的应用直接运行在宿主机的内容，容器是没有自己的内核的，也没有虚拟硬件。
3. 每个容器都是相互隔离的，每个容器都有属于自己的文件系统，互不影响。

容器化带来的好处：

1. 简化配置

   这是Docker初始目的，虚拟机VM最大的好处是基于你的应用配置能够无缝运行在任何平台上。Docker提供同样类似VM的能力，但是没有任何副作用，它能让你将环境和配置放入代码然后部署，同样的Docker配置能够在各种环境中使用，这实际是将应用环境和底层环境实现了解耦。

2. 代码管道化管理
   能够对代码以流式pipeline管道化进行管理，从开发者的机器到生产环境机器这个流程中都能有效管理。因为在这个流程中会有各种不同的环境，每个都可能有微小的区别，Docker提供了跨越这些异构环境以一致性的微环境，从开发到部署实现流畅发布。

3. 开发人员的生产化
   在一个开发环境，我们希望我们的开发环境能更加接近于生产环境，我们会让每个服务运行在自己的VM中，这样能模拟生产环境，比如有时我们并不总是需要跨越网络连接，这样我们可以将多个Docker装载一系列服务运行在单机上最大程度模拟生产分布式部署的环境。

4. 应用隔离
   有很多理由你需要在一台机器上运行多个应用，这就需要将原来铁板一块monolithic的应用切分为很多微服务。实现应用之间的解耦，将多个应用服务部署在多个Docker中能轻松达到这个目的。

5. 服务合并
   使用Docker也能合并多个服务以降低费用，不多的操作系统内存占用，跨实例共享多个空闲的内存，这些技术Docker能以更加紧密资源提供更有效的服务合并。

6. 多租户
   Docker能够作为云计算的多租户容器，使用Docker能容易为每个租户创建运行应该多个实例，这得益其灵活的快速环境以及有效diff命令。

7. 快速部署
   Docker通过创建进程的容器，不必重新启动操作系统，几秒内能关闭，你可以在数据中心创建或销毁资源，不用担心额外消耗。典型的数据中心利用率是30%，通过更积极的资源分配，以低成本方式对一个新的实例实现一个更聚合的资源分配，我们很容易超过这个利用率，大大提高数据中心的利用效率。

### 3、Docker的组成

![img](https://img-blog.csdn.net/20180525171652596)

如图所示：

主要有Docker Client客户端、Docker daemon守护进程、Docker Image镜像、Docker Comtainer容器。

1. Docker Client客户端和Docker daemon守护进程：
   Docker是C/S（客户端client-服务器server）架构模式。Docker通过客户端连接守护进程，通过命令向守护进程发出请求，守护进程通过一系列的操作返回结果。Docker客户端可以连接本地或者远程的守护进程。Docker客户端和服务器通过socket或RESTful API进行通信。

2. Docker Image镜像：

   镜像是容器的基石，容器基于镜像启动和运行。镜像就好像容器的源代码，保存了容器各种启动的条件。镜像是一个层叠的只读文件系统。

3. Docker Comtainer容器：

   容器通过镜像来启动，容器是Docker的执行来源，可以执行一个或多个进程。镜像相当于构建和打包阶段，容器相当于启动和执行阶段。容器启动时，Docker容器可以运行、开始、停止、移动和删除。每一个Docker容器都是独立和安全的应用平台。

4. Docker Registry仓库：

   Docker仓库用来保存镜像。Docker仓库分为公有和私有。Docker公司提供公有仓库Docker hub,网址：https://hub.docker.com/。
   
   我们也可以创建自己私有的仓库。

### 4、Docker的安装



### 5、Docker的一些命令

###### 1、基础命令

```
sudo systemctl start docker	# systemctl检查系统与服务管理器
systemctl restart docker
docker info
docker pull [container name]
docker run [container name]
docker run -it [name]:[tag] /bin/bash # -it开启虚拟终端，/bin/bash保持容器存在一个进程在运行
docker ps /	docker ps -a
docker logs / docker port 
docker restart [name id]
docker stop [name id]
docker run -itd --name test [name] /bin/bash
容器进入后台运行使用：
docker attach [container id] # 进入虚拟终端执行退出同时导致容器停止
docker exec -it [container id] /bin/bash # 进入虚拟终端执行退出不会导致容器停止
docker container prune	# 清理所有处于终止状态的容器
docker top # 查看容器内运行的进程
docker inspect [docker name] # 返回容器的配置和状态信息
```

###### 2、镜像

```
docker rmi [image id]
docker images
# 提交更改的镜像
docker commit -m="has update" -a="runoob" e218edb10161 runoob/ubuntu:v2
docker commit -m="[update inf]" -a="[auther]" [image id] [image name]:v2
# 修改镜像的tag
docker tag 860c279d2fec runoob/centos:dev
docker tag [container id] [container name]:[tag]
```

###### 3、容器连接

```
-P :是容器内部端口随机映射到主机的高端口。
-p :是容器内部端口绑定到指定的主机端口。
docker run -d -p 5000:5000 training/webapp python app.py # 可以绑定网址和端口
docker run -d -P --name TestRename training/webapp python app.py # --name为运行的容器重命名
# -p 3344:80 为将容器内的80端口映射到容器外的3344端口，可以在外部网络访问容器内部署的的内容。（端口暴露）
docker network create -d bridge test-net # 创建Docker网络
docker run -itd --name test1 --network test-net ubuntu /bin/bash # 运行容器连接到一个网络
# 在CentOS & Ubuntu中安装ping
apt-get update
apt install iputils-ping
将下列内容添加到宿主机/etc/docker/daemon.json中，后续所有运行的容器DNS都会被配置成为以下内容。
{
  "dns" : [
    "114.114.114.114",
    "8.8.8.8"
  ]
}

docker run -it --rm -h host_ubuntu  --dns=114.114.114.114 --dns-search=test.com ubuntu

```

###### 4、仓库管理

```
docker login # 登录到docker hub
docker search [image name] # 查找镜像
docker push username/ubuntu:18.04 # 推送到账号的仓库
docker search username/ubuntu
```

###### 5、镜像原理

- **联合文件系统：**

以下图各个镜像为例：

![img](https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fimg2020.cnblogs.com%2Fblog%2F1070925%2F202010%2F1070925-20201007122257922-757623315.png&refer=http%3A%2F%2Fimg2020.cnblogs.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=jpeg?sec=1640767396&t=c3f861e026a51ec80278e7d04f4e33d9)

在各个镜像安装的过程中是分层安装的，所需的基础模块会独立的从云端仓库下载到本地，当`image1`与`image2`有共同的基础模块时，只需要下载一次此基础模块，而`image1`和`image2`会共用此一个基础模块，节省资源。

docker运行在Linux宿主机上，各个镜像共同使用宿主机的Linux内核，而镜像中保留了最基础最小可以使镜像正常运行的必须模块，从而达到资源的最大化利用。

- **镜像的分层理解：**

关于镜像的分层，每个镜像为一个完整的文件，以`ubuntu`和`Nginx`为例，在下载安装时会按照联合系统文件的方式对所需要的基础模块进行处理。当运行某个镜像成为一个容器之后，对其基础模块不能进行改变。

以下图为例：镜像运行后，镜像层被锁定不可更改，容器层可以进行处理和更改，添加其他组件或者添加新内容。而后可以将其更改的内容与之前的镜像层重新打包成为一个新的镜像，新的镜像运行成为容器之后与下图原理相同。

![img](https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fimgedu.lagou.com%2F952033-20180526102212000-1205998304.png&refer=http%3A%2F%2Fimgedu.lagou.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=jpeg?sec=1640766960&t=8cf78df1a3b0e1297654608cc4815cc1)

### 6、Docker Volume





### 7、Dockerfile

用来创建镜像的文本文件，文本内容包含了一条条构建镜像所需的指令和说明。

在空文件夹下面创建Dockerfile文件，添加以下内容：

```
FROM nginx
RUN echo '这是一个本地构建的nginx镜像' > /usr/share/nginx/html/index.html
```

Dockerfile 的指令每执行一次都会在 docker 上新建一层。所以过多无意义的层，会造成镜像膨胀过大。

```
FROM centos
RUN yum -y install wget
RUN wget -O redis.tar.gz "http://download.redis.io/releases/redis-5.0.3.tar.gz"
RUN tar -xvf redis.tar.gz
以上会建立三层镜像，使用以下格式进行简化：
FROM centos
RUN yum -y install wget \
    && wget -O redis.tar.gz "http://download.redis.io/releases/redis-5.0.3.tar.gz" \
    && tar -xvf redis.tar.gz
使用 && 连接之后就只建立一层镜像。
```

```
docker build -t nginx:v3 .
使用docker build 命令在 Dockerfile 目录下建立新的镜像文件。. 表示当前文件。
```

### 8、Docker  Compose

Docker-Compose项目是Docker官方的开源项目，负责实现对Docker容器集群的快速编排。使用Docker-Compose的步骤：

- 使用 Dockerfile 定义应用程序的环境
- 使用 docker-compose.yml 定义构成应用程序的服务，这样它们可以在隔离环境中一起运行。
- 最后，执行 docker-compose up 命令来启动并运行整个应用程序。

```
# 安装
$ sudo curl -L "https://github.com/docker/compose/releases/download/1.24.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
# 将可执行权限应用于二进制文件
$ sudo chmod +x /usr/local/bin/docker-compose
# 创建软连接
$ sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
# 测试是否连接成功
$ docker-compose --version
docker-compose version 1.24.1, build 4667896b
# 以此为例启动docker-compose
https://www.runoob.com/docker/docker-compose.html
其中需要依赖GCC，需要先安装GCC.
docker-compose up
docker-compose -d # 后台运行
```

### 9、Docker Machine

Docker Machine 是一种可以让您在虚拟主机上安装 Docker 的工具，并可以使用 docker-machine 命令来管理主机。Docker Machine 也可以集中管理所有的 docker 主机，比如快速的给 100 台服务器安装上 docker。Docker Machine 管理的虚拟主机可以是机上的，也可以是云供应商，如阿里云，腾讯云，AWS，或 DigitalOcean。使用 docker-machine 命令，您可以启动，检查，停止和重新启动托管主机，也可以升级 Docker 客户端和守护程序，以及配置 Docker 客户端与您的主机进行通信。

安装

```
# 使用以下命令安装Docker Machine
base=https://github.com/docker/machine/releases/download/v0.16.0 &&
  curl -L $base/docker-machine-$(uname -s)-$(uname -m) >/tmp/docker-machine &&
  sudo mv /tmp/docker-machine /usr/local/bin/docker-machine &&
  chmod +x /usr/local/bin/docker-machine
# 查看版本
docker-machine version
# 创建一个虚拟机
docker-machine create --driver virtualbox test

```

在CentOS上安装VirtualBox参考及相关问题：

```
https://www.linuxidc.com/Linux/2018-11/155220.htm # 安装
https://blog.csdn.net/fly_leopard/article/details/93207291 # 无法启动，内核版本不一样。
```

Docker Machine 已被弃用。请改用 Docker 桌面。请参 阅[Docker Desktop for Mac](https://docs.docker.com/desktop/mac/)和[Docker Desktop for Windows](https://docs.docker.com/desktop/windows/)。还可以使用其他云预配工具。

### 10、Swarm 集群管理

Docker Swarm 是 Docker 的集群管理工具。它将 Docker 主机池转变为单个虚拟 Docker 主机。 Docker Swarm 提供了标准的 Docker API，所有任何已经与 Docker 守护程序通信的工具都可以使用 Swarm 轻松地扩展到多个主机。

















