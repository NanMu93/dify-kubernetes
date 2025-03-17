# DIFY-KUBERNETES

dify-kubernetes is used to deploy Dify to a Kubernetes cluster.

## Installation

1. Clone the current repository `git clone https://github.com/NanMu93/dify-kubernetes.git`
2. Enter the project directory `cd dify-kubernetes`
3. Run `kubectl apply -f dify-kubernetes.yaml`
4. Wait for the deployment to complete

## Configuration

### Environment Variables

You can modify the environment variable configuration in the `dify-env` and other `env` `ConfigMap` objects.

### Passwords

You can configure your own `redis` and `postgres` passwords in the `Secret` object.