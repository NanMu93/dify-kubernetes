# DIFY-KUBERNETES

dify-kubernetes用于部署Dify的kubernetes集群。

## 安装

1. 克隆当前仓库`git clone https://github.com/NanMu93/dify-kubernetes.git`
2. 进入到项目目录`cd dify-kubernetes`
3. 执行`kubectl apply -f dify-kubernetes.yaml`
4. 等待部署完成

## 配置

###  env

可以在`dify-env`及其他`env`的`ConfigMap`中修改环境变量的配置。

###  password

可以在`Secret`中配置你自己的`redis`、`postgres`密码。
