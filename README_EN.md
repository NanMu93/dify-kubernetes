# DIFY-KUBERNETES

dify-kubernetes is used to deploy Dify's kubernetes cluster with one click.
Current update version is Dify v1.1.3

## Installation

1. Clone the current repository `git clone https://github.com/NanMu93/dify-kubernetes.git`
2. Enter the project directory `cd dify-kubernetes`
3. Run `kubectl apply -f dify-kubernetes.yaml`
4. Wait for the deployment to complete
5. Access Dify (default nginx service is exposed to the node's 30000 port through NodePort, please make sure the node where nginx is deployed is accessible)
    `http://<your-node-ip>:30000`

## Configuration

###  env

You can modify the environment variable configuration in the `dify-env` and other `env` ConfigMaps.

###  password

You can configure your own `redis` and `postgres` passwords in the Secret.

## Dify Plugin Development and Debugging Interface

Currently, the debugging port for the Dify plugin has been changed to the NodePort type, with the port number set to `31000`. The IP address corresponds to the Kubernetes node IP where the `dify-plugin-debug` `service` is running. 

If you need to develop your own plugins, refer to the official documentation: [develop plugins](https://docs.dify.ai/zh-hans/plugins/quick-start/develop-plugins)

## Improvements

1. You can use PersistentVolume instead of HostPath to improve the security of the storage.
2. If you are using an internal LoadBalancer, you can use LoadBalancer instead of NodePort.
3. It is recommended to set your own password and API key.
