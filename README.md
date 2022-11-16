# gitops-playground

Setup k8s clusters using argo-cd.

## bootstrap argo install
```
kubectl apply -k argo-cd/
```

## get initial admin secret
```
kubectl get secret/argocd-initial-admin-secret -o jsonpath='{.data.password}' -n argocd | base64 -d; echo
```

## expose argo ui
```
kubectl port-forward argocd/argocd-server -n argocd 8443:443
```
