# ConfigMap和Secret：配置应用程序

## 一、配置容器化应用程序

- 向容器传递命令行参数
- 为每个容器设置自定义环境变量
- 通过特殊类型的卷将配置文件挂载到容器中

## 二、向容器传递命令行参数

### 1.在Docker中定义命令与参数

- 了解ENTRYPOINT与CMD
- 了解shell与exec形式的区别
- 可配置化fortune镜像中的间隔参数

### 2.在Kubernetes中覆盖命令与参数

- 用自定义间隔值运行fortune pod

## 三、为容器设置环境变量

- 通过环境变量配置化fortune镜像中的间隔值

### 1.在容器定义中指定环境变量

### 2.在环境变量中引用其他环境变量

### 3.了解硬编码环境变量的不足之处

## 四、利用ConfigMap解耦配置

### 1.ConfigMap介绍

### 2.创建ConfigMap

- 使用 指令 kubectl创建ConfigMap
- 从文件内容创建ConfigMap条目
- 从文件夹创建ConfigMap
- 合并不同选项

### 3.给容器传递ConfigMap条目作为环境变量

- 在pod中引用不存在的ConfigMap

### 4.一次性传递ConfigMap的所有条目作为环境变量

### 5.传递ConfigMap条目作为命令行参数

### 6.使用configMap卷将条目暴露为文件

- 创建ConfigMap
- 在卷卷内使用ConfigMap的条目
- 检查Nginx是否使用被挂载的配置文件
- 检查被挂载的configMap卷的内容
- 卷内暴露指定的ConfigMap条目
- 挂载某一文件夹会隐藏该文件夹中已存在的文件
- ConfigMap独立条目作为文件被挂载且不隐藏文件夹中的其他文件
- 为ConfigMap卷中的文件设置权限

### 7.更新应用配置且不重启应用程序

- 修改ConfigMap
- 通知Nginx重载配置
- 了解文件被自动更新的过程
- 挂载至已存在文件夹的文件不会被更新
- 了解更新ConfigMap的影响

## 五、使用Secret给容器传递敏感数据

### 1.介绍Secret

### 2.默认令牌Secret的介绍

### 3.创建 Secret

### 4.对比ConfigMap与Secret

- 为二进制数据创建Secret
- stringData字段介绍
- 在pod中读取Secret条目

### 5.在pod中使用Secret

- 修改fortune-ConfigMap以开启HTTPS
- 挂载fortune-secret至pod
- 测试Nginx是否正使用Secret中的证书与私钥
- Secret卷存储于内存
- 通过环境变量暴露Secret条目
- 了解镜像拉取Secret
- 在Docker Hub上使用私有镜像仓库
- 创建用于Docker镜像仓库鉴权的Secret
- 在pod定义中使用docker-registry Secret
- 不需要为每个pod指定镜像拉取Secret

## 六、本章小结

- 在pod定义中覆盖容器镜像定义的默认命令
- 传递命令行参数给容器主进程
- 为容器设置环境变量
- 将配置从pod定义中分离并放入ConfigMap
- 通过Secret存储敏感数据并安全分发至容器
- 创建docker-registry Secret用以从私有镜像仓库拉取镜像

