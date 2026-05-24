# oci-free-k8s-cluster-apps

Kubernetes application configuration for the
[oci-free-k8s-cluster](https://github.com/davidconalrobinson/oci-free-k8s-cluster)
repository.

Each top-level directory is a Kustomize overlay intended to be deployed by
Argo CD into the always-free OCI Kubernetes cluster:

- `argocd-ingress`
- `cert-manager`
- `external-dns`
- `ingress-nginx`
- `oauth2-proxy`
- `sops-secrets-operator`

The overlays use Kustomize's Helm chart generator, so local rendering requires
both `kubectl` and `helm`.

```sh
kubectl kustomize <app-directory> --enable-helm
```

Encrypted secrets are managed with
[SOPS](https://github.com/getsops/sops) and the
[sops-secrets-operator](https://github.com/isindir/sops-secrets-operator).

## CI

GitHub Actions renders every top-level Kustomize overlay on pushes to `master`
and on pull requests. This is a lightweight check that validates the local
Kustomize and Helm inputs without needing access to a Kubernetes cluster.
