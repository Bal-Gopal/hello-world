# hello-world

A minimal repository that prints "Hello, world!".

## Argo CD

- **Application manifest**: [argocd/application.yaml](argocd/application.yaml)
- **Kubernetes manifests**: [k8s/deployment.yaml](k8s/deployment.yaml), [k8s/service.yaml](k8s/service.yaml)

To use this with Argo CD:

1. Replace the `repoURL` in `argocd/application.yaml` with your repository URL (for example `https://github.com/your-user/hello-world`).
2. Commit and push these files to your remote repository.
3. Apply the Argo CD Application (or create it in the Argo CD UI):

```bash
# (after installing Argo CD and ensuring kubectl is configured)
kubectl apply -f argocd/application.yaml -n argocd
```

Argo CD will read the `k8s` path in the repository and deploy the `Deployment` and `Service` resources.

Git push example:

```bash
git add argocd k8s README.md
git commit -m "Add Argo CD Application and simple k8s manifests"
git push origin main
```

