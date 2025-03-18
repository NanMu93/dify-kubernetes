# DIFY-KUBERNETES

dify-kubernetes用于一键部署Dify的kubernetes集群。
当前更新版本为Dify v1.0.1

## 安装

1. 克隆当前仓库`git clone https://github.com/NanMu93/dify-kubernetes.git`
2. 进入到项目目录`cd dify-kubernetes`
3. 执行`kubectl apply -f dify-kubernetes.yaml`
4. 等待部署完成
5. 访问dify（默认通过NodePort暴露nginx服务到节点的30000端口，请确定nginx被部署到的节点）
    `http://<your-node-ip>:30000`

## 配置

###  env

可以在`dify-env`及其他`env`的`ConfigMap`中修改环境变量的配置。

###  password

可以在`Secret`中配置你自己的`redis`、`postgres`密码。

## 改进
1. 可以使用PersistentVolume替代HostPath以提高存储的安全性。
2. 如果你使用了内置的LoadBalancer，可以使用LoadBalancer替代NodePort。
3. 建议设置你自己的密码和API KEY。