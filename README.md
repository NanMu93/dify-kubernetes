# DIFY-KUBERNETES

dify-kubernetes用于一键部署Dify的kubernetes集群。
当前更新版本为Dify v1.1.3

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

## dify plugin 开发调试接口

目前将dify plugin的调试端口改为NodePort类型，端口号为`31000` ，IP地址为你的运行`dify-plugin-debug` `service`的kubernetes节点IP。
如果有需要自己开发插件，参照官方文档：[插件开发](https://docs.dify.ai/zh-hans/plugins/quick-start/develop-plugins)

## 改进
1. 可以使用PersistentVolume替代HostPath以提高存储的安全性。
2. 如果你使用了内置的LoadBalancer，可以使用LoadBalancer替代NodePort。
3. 建议设置你自己的密码和API KEY。
