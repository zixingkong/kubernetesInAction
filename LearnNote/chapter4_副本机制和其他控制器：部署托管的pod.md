# 副本机制和其他控制器：部署托管的pod

## 一、保持pod健康

### 1.介绍存活探针

### 2.创建基于HTTP的存活探针

### 3.使用存活探针

### 4.配置存活探针的附加属性

### 5.创建有效的存活探针

- 存活探针应该检查什么
- 保持探针轻量
- 无需在探针中实现重试循环
- 存活探针小结

## 二、了解ReplicationController

### 1.ReplicationController的操作

- 介绍控制器的协调流程
- 了解ReplicationController的三个部分
- 更改控制器的标签选择器或pod模板的效果
- 使用ReplicationController的好处

### 2.创建一个ReplicationController

### 3.使用ReplicationController

- 查看ReplicationController对已删除pod的响应
- 获取有关ReplicationController的信息
- 控制器如何创建新的pod
- 应对节点故障

### 4.将pod移入或移出ReplicationController的作用域

- 给ReplicationController管理的pod加标签
- 更改已托管的pod的标签
- 从控制器删除pod
- 更改ReplicationController的标签选择器

### 5.修改pod模板

### 6.水平缩放pod

- ReplicationController扩容
- 通过编辑定义来缩放ReplicationController
- 用kubectl scale命令缩容
- 伸缩集群的声明式方法

### 7.删除一个ReplicationController

## 三、使用ReplicaSet而不是ReplicationController

### 1.比较ReplicaSet和ReplicationController

### 2.定义ReplicaSet

### 3.创建和检查ReplicaSet

### 4.使用ReplicaSet更富表达力的标签选择器

### 5.ReplicaSet小结

## 四、使用DaemonSet在每个节点上运行一个pod

### 1.使用DaemonSet在每个节点上运行一个pod

### 2.使用DaemonSet只在特定的节点上运行pod

- 用一个例子来解释DaemonSet
- 创建一个DaemonSet YAML文件
- 创建DaemonSet
- 向节点上添加所需的标签
- 从 节点上删除所需的标签

## 五、运行执行单个任务的pod

### 1.介绍Job资源

### 2.定义Job资源

### 3.看Job运行一个pod

### 4.在Job中运行多个多个pod实例

- 顺序运行Job pod
- 并行运行Job pod
- Job的缩放

### 5.限制Job pod完成任务的时间

## 六、安排Job定期运行或在将来运行一次

### 1.创建一个CronJob

- 配置时间表安排

### 2.了解计划任务的运行方式

## 七、本章小结

- 使用存活探针，让Kubeme tes在容器不再健康的情况 下立即重 启它（应用程序定义了健康的条件）。
- 不应该直接创建pod , 因为如果 它们被错误地删除，它们正在运行的节点异常，或者它们从节点中被逐出时， 它们将不会被重新创建。
-  ReplicationController始终保持所需 数量的pod 副本正在运行。
- 水平缩放pod与在ReplicationController上更改所需的副本个数 一 样简单。
-  pod 不属千ReplicationController, 如有必要可以在它们之间移动 。
- ReplicationController 将 从pod模板 创建新的pod。更改模板对现有的pod没有影响。
- ReplicationController 应该替换为 ReplicaSe t和Deployment, 它们提供相同的能力， 但具有额外的强大功能。
- ReplicationController 和 ReplicaSet 将 pod 安排到随机集群节点， 而 DaemonSet确保每个节点都运行 一 个 DaemonSet 中定义的 pod 实例。
- 执行批处理任务的 pod 应通过 Kubernetes Job 资源创建， 而不是直接或通过ReplicationController 或类似对象创建。
- 需要在未来某个时候运行的 Job 可以通过 CronJob 资源创建。