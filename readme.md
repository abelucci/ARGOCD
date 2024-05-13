# **COMANDOS CLI ARGO**

Instalar el chart de ArgoCD para poder manipular archivos de manifiesto, como tambien el CLI de Argo.

* Lanzar proxy argo para poder levantar Argo sin exponer el servicio, se recomienda utilizar otra terminar:

```
kubectl port-forward svc/argocd-server -n argocd 8080:443
```

* Verificar la clave de admin:

```
argocd admin initial-password -n argocd
```

* Loguerase:

```
argocd login localhost:8080
```

* Crear proyecto:

```
argocd app create pokedex-local-it --repo https://github.com/abelucci/KUBERNETES.git --path POKEDEX --dest-server https://kubernetes.default.svc --dest-namespace default
```

* Verificar proyectos creados:

```
kubectl get applications -n argocd
```
