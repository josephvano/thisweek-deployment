# thisweek deployment repository

This repository contains kubernetes manifests and follows GitOps flow.


```bash
kubectl create namespace ns thisweek-app
kubectl apply -f . -n thisweek-app
```

Run the following command to test this applicaiton

```bash
kubectl port-forward svc/thisweek-app 8080:8083 -n thisweek-app
```

# Deploy on ArgoCD

ArgoCD is a GitOps operator for Kubernetes that enables GitOps strategy

Run the following command on your kubernetes cluster

```bash
argocd app create thisweek-app \
--repo https://github.com/<username>/thisweek \
--path . \
--dest-server https://kubernetes.default.svc \
--dest-namespace default
``` 
