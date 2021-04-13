# 服务：让客户端发现pod并与之通信

## 一、介绍服务

结合实例解释服务

### 1. 创建服务

- 通过kubectl expose创建服务
- 通过YAML描述文件创建服务
- 检测新的服务
- 从内部集群测试服务
- 在运行的容器中远程执行命令
- 配置服务上的会话亲和性
- 同一个服务暴露多个端口
- 使用命名的端口

### 2.服务发现

- 通过环境变量发现服务
- 通过DNS发现服务
- 通过FQDN连接服务
- 在pod容器中运行shell
- 无法ping通服务IP的原因

## 二、连接集群外部的服务

### 1.介绍服务endpoint

### 2.手动配置服务的endpoint

- 创建没有选择器的服务
- 为没有选择器的服务创建endpoint资源

### 3.为外部服务创建别名

## 三、将服务暴露给外部客户端

### 1.使用NodePort类型的服务

- 创建NodePort类型的服务
- 查看NodePort类型的服务
- 更改防火墙规则，让外部客户端访问我们的NodePort服务

### 2.通过负载均衡器将服务暴露出来

- 创建LoadBalance服务
- 通过负载均衡器连接服务

### 3.了解外部连接的特性

- 了解并防止不必要的网络跳数
- 记住客户端IP是不记录的

## 四、通过Ingress暴露服务

- 为什么需要Ingress
- Ingress控制器是必不可少的

### 1.创建Ingress资源

### 2.通过Ingress访问服务

- 获取Ingress的IP地址
- 确保在Ingress中配置的Host指向Ingress的IP地址
- 通过Ingress访问pod
- 了解Ingress的工作原理

### 3.通过相同的Ingress暴露多个服务

- 将不同的服务映射到相同主机的不同路径
- 将不同的服务映射到不同的主机上

### 4.配置Ingress处理TLS传输

- 为Ingress创建TLS认证

## 五、pod就绪后发出信号

### 1.介绍就绪探针

- 就绪探针的类型
- 了解就绪探针的操作
- 了解就绪探针的重要性

### 2.向pod添加就绪探针

- 向pod template添加就绪探针
- 观察并修改pod就绪状态
- 服务打向单独的pod

### 3.了解就绪探针的实际作用

- 务必定义就绪探针
- 不要将停止pod的逻辑纳入就绪探针中

## 六、使用headless服务发现独立的pod

### 1.创建headless服务

### 2.通过DNS发现pod

- 不通过YAML文件运行pod
- 理解headless服务的DNS A记录解析

### 3.发现所有的pod-包括未就绪的pod

## 七、排除服务故障

 首先， 确保从集群内连接到服务的集群IP, 而不是从外部。

- 不要通过ping服务IP 来判断服务是否可 访问（请记住， 服务的集群IP 是虚
  拟IP, 是无法ping通的）。
- 如果已经定义了就绪探针， 请确保 它返回成功；否则该pod不会成为服务的
  一部分 。
-  要确认某个容器是服务的 一 部分， 请使用kubectl getendpoints 来检
  查相应的端点对象。
- 如 果尝试通过FQDN或其中一 部 分来访问服务（例如， myservice.
  mynamespace.svc.cluster.local 或 myservice.mynamespace), 但
  并不起作用， 请查看是否可以使用其集群IP而不是FQDN来访问服务 。
- 检查是否连接到服务公开的端口，而不是目标端口 。
- 尝试直接连接到podIP以确认pod正在接收正确端口上的 连接。
- 如果甚至无法通过pod的IP 访问应用， 请确保应用不是仅绑定 到本地主机。

## 八、本章小结

在一个固定的IP地址和端口下暴露匹配到某个标签选择器的多个pod

- 服务在集群内默认是可访问的， 通过将服务的 类型设置为NodePort或
  LoadBalancer, 使得服务也可以从集群外部访问
- 让pod能够通过查找环境变量发现服务的IP地址和端口
- 允许通过创建服务资源而不指定选择器来发现驻留在集群外部的服务并与之
  通信， 方法是创建 关联的Endpoint 资源
- 为具有ExternalName服务类型的外部服务提供DNSCNAME别名
- 通过单个Ingress公开多个HTTP服务（使用单个IP)
- 使用pod容器的就绪探针来确定是否应该将pod包含在服务endpoint s内
- 通过创建 headless服务让DNS发现 pod IP
  随着对服务的深入理解， 也学习到了下面的内容：
  - 故障排查
  - 修改GoogleKubemet es/ Compute Eng in e中的防火墙规则
  - 通过 kubec七l exec在 pod容器中执行命令
  - 在现有容器的容器中运行 一 个bash shell
  - 通过 kubectl apply命令修改Kubemet es资源
  -  使用 kubectl run --generator= run-pod/vl运行临时的pod