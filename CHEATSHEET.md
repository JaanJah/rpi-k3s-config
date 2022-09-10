# Cheatsheet

This document contains some useful resources for managing my k3s instance.


### Restart k3s

```sh
sudo systemctl restart k3s
```
### Automatically Deploying Manifests and Helm Chartslink

Any Kubernetes manifests found in /var/lib/rancher/k3s/server/manifests will automatically be deployed to K3s in a manner similar to kubectl apply. Manifests deployed in this manner are managed as AddOn custom resources, and can be viewed by running kubectl get addon -A. You will find AddOns for packaged components such as CoreDNS, Local-Storage, Traefik, etc. AddOns are created automatically by the deploy controller, and are named based on their filename in the manifests directory.

It is also possible to deploy Helm charts as AddOns. K3s includes a Helm Controller that manages Helm charts using a HelmChart Custom Resource Definition (CRD).

- https://rancher.com/docs/k3s/latest/en/helm/#automatically-deploying-manifests-and-helm-charts
