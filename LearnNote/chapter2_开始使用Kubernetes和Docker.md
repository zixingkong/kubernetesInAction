# chapter2_开始使用Kubernetes和Docker

## 一、创建、运行和共享容器镜像

### 1. 安装Docker并运行Hello World容器

- 运行Hello World容器
- 背后的原理
- 运行其他镜像
- 容器镜像的版本管理

### 2. 创建一个简单的Node.js应用

### 3.为镜像创建Dockerfile

### 4.构建容器镜像

- 镜像是如何构建的
- 镜像分层
- 比较使用DockerFile和手动构建镜像

### 5.运行容器镜像

- 访问应用
- 列出所有运行中的容器
- 获取更多的容器信息

### 6.探索运行容器的内部

- 在已有的容器内部运行shell
- 从内部探索容器
- 容器内的进程运行在主机操作系统上
- 容器的文件系统也是独立的

### 7.停止和删除容器

### 8.向镜像仓库推送镜像

- 使用附加标签标注镜像
- 向Docker Hub推送镜像
- 在不同机器上运行镜像

## 二、配置Kubernetes集群

### 1.用Minikube运行一个本地单节点的Kubernetes集群

- 安装Minikube
- 使用MiniKube启动一个Kubernetes集群
- 安装Kubernetes客户端(kubectl)
- 使用kubectl查看集群是否正常工作

### 2.使用Google Kubernetes Engine托管Kubernetes集群

- 配置一个Google Cloud项目并且下载必需的客户端二进制
- 创建一个三节点Kubernetes集群
- 获取集群概览
- 通过列出集群节点查看集群是否在运行
- 查看对象的更多信息

### 3.为kubectl配置别名和命令行补全

- 创建别名
- 为Kubectl配置tab补全

## 三、在Kubernetes上运行第一个应用

### 1.部署Node.js应用

- 介绍pod
- 列出pod
- 幕后发生的事情

### 2.访问Web应用

- 创建一个服务对象
- 列出服务
- 使用外部ＩＰ访问服务

### 3.系统的逻辑部分

- ReplicationController、pod和服务是如何组合在一起的
- Pod和它的容器
- ReplicationController的角色
- 为什么需要服务

### 4.水平伸缩应用

- 增加期望的副本数
- 查看扩容的结果
- 当切换到服务时请求切换到所有三个pod上
- 可视化系统的新状态

### 5.查看应用运行在哪个节点上

- 列出pod时显示pod IP 和pod的节点
- 使用kubectl describe查看pod的其他细节

### 6.介绍Kubernetes dashboard

- 访问GKE集群的dashboard
- 访问Minikube的dashboard

## 本章小结

-  拉取并且运行任何公开的镜像。
- 把应用打包成容器镜像， 并且推送到远端的公开镜像仓库让大家都可以使用。
-  进入运行中的容器并检查运行环境。
- 在 GKE 上创建 一 个多节点的 K8s 集群。
-  为 kubec七1 命令行工具设置别名和 tab 补全。
- 在 Kubernetes 集群中列出查看节点、 pod、 服务和 ReplicationController。
- 在 Kubernetes 中运行容器并可以在集群外访问。
- 了解 pod、 ReplicationController 和服务是关联的基础场景。
- 通过改变 ReplicationController 的复本数对应用进行水平伸缩。
- 在 Minikube 和 GKE 中访问基于 web 的 Kubernetes dashboard。

