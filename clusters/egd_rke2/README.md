# Setup

Install ArgoCD

```
helm upgrade --install \
  argocd argo-cd \
  --repo https://argoproj.github.io/argo-helm \
  --create-namespace \
  --namespace argocd \
  --wait
```

Apply ArgoCD Application of Applications:

```
kubectl apply -f _app_of_apps/app_of_apps.yml
```

Or apply from GitHub:

```
kubectl apply -f https://raw.githubusercontent.com/sika-training-examples/2026-02-27_edg-kubernetes-example-final/refs/heads/master/clusters/egd_rke2/_app_of_apps/app_of_apps.yml
```

Refresh ArgoCD App of Apps in using kubectl:

```
kubectl annotate application -n argocd app-of-apps-egd-rke2 argocd.argoproj.io/refresh=hard --overwriteapplication.argoproj.io/app-of-apps-egd-rke2
```

See: http://argocd-egd-rke2.sikademo.com/
