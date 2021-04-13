# chapter1_Kubernetes介绍

## 一、Kubernetes系统的需求

### 1. 从单体应用到微服务

- 将应用拆解为多个微服务
- 微服务的扩容
- 部署微服务
- 环境需求的差异

### 2. 为应用程序提供一个一致的环境

### 3. 迈向持续交付：DevOps和无运维

- 带来的优点
- 让开发者和系统管理员做他们最擅长的

## 二、介绍容器技术

### 1.什么是容器

- 用Linux技术隔离组件
- 比较虚拟机和容器
- 容器实现隔离机制介绍
- 用Linux命名空间隔离进程
- 限制进程的可用资源

### 2.Docker容器平台介绍

- Docker的概念
  - 镜像
  - 镜像仓库
  - 容器
- 构建、分发和运行Docker镜像
- 对比虚拟机 和Docker容器
- 镜像层
- 容器镜像可移植性的限制

### 3. rkt-----一个Docker的替代方案

## 三、Kubernetes介绍

### 1.初衷

### 2.深入浅出地了解Kubernetes

- Kubernetes的核心功能
- 帮助开发者聚焦核心应用功能
- 帮助运维团队获取更高的资源利用率

### 3.Kubernetes集群架构

- 控制面板
  - Kubernetes API服务器
  - Schedule
  - Controller Manager
  - etcd
- 工作节点
  - Docker、rkt或其他的容器类型
  - Kubelet
  - Kubernetes Service Proxy

### 4.在Kubernetes中运行应用

- 描述信息怎样成为一个运行的容器
- 保持容器运行
- 扩展副本数量
- 命中移动目标

### 5. 使用Kubernetes的好处

- 简化应用程序部署
- 更好地利用硬件
- 健康检查和自修复
- 自动扩容
- 简化应用部署

## 四、本章小结

- 单体应用程序更容易部署，但随着时间的推移更难维护，并且有时难以扩展
- 基于微服务的应用程序体系结构使每个组件的开发更容易，但是很难配置和部署它们作为单个系统工作
- Linux容器提供的好处与虚拟机差不多，但他们轻量很多，并且允许更好地利用硬件
- 通过允许更简单快捷地将容器化应用和其操作系统环境一起管理，Docker改进了现有的Linux容器技术
- Kubernetes将整个数据中心暴露为用于运行应用程序的单个计算资源
- 开发人员可以通过Kubernetes部署应用程序，而无需系统管理员的帮助
- 通过让Kubernetes自动地处理故障节点，系统管理员可以睡得更好

```shell
 sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
```
