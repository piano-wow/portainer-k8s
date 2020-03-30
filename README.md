# Portainer on Kubernetes BETA

This repository contains all the manifests you can use to deploy the Portainer for Kubernetes BETA version.

For any feedback regarding the BETA version, please head to the [portainer for Kubernetes BETA repository](https://github.com/portainer/kubernetes-beta).

These manifests have been tested on:

* Azure AKS
* Digital Ocean
* minikube
* kind

Have any feedback on the deployment of Portainer inside Kubernetes? Please head to the [deployment feedback topic](https://github.com/portainer/kubernetes-beta/issues/1).

# Usage

## Deploy Portainer inside your cluster and access it via an external load balancer

If your cloud provider supports external load balancers, you can use the following command to deploy Portainer:

```
kubectl ... apply -f portainer.yaml
```

This will deploy the Portainer application and create an external load balancer which you'll be able to use to access Portainer on port 9000.

## Deploy Portainer inside your cluster and access it via node port

If you prefer to access Portainer via a specific port on a node of your cluster, use the following command:

```
kubectl ... apply -f portainer-nodeport.yaml
```

This will expose Portainer on the port `30777` inside your cluster. You can change that port inside the manifest if you wish.

## Manage a remote Kubernetes cluster

In order to manage a remote Kubernetes cluster, you'll need a Portainer for Kubernetes BETA instance already deployed inside a Kubernetes cluster and connect it to a Portainer agent running inside the remote cluster. See the agent folder for how to deploy the agent inside a Kubernetes cluster.
