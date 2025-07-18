# ArgoCD Repository

This repository contains the configuration and manifests for deploying and managing [ArgoCD](https://argo-cd.readthedocs.io/) in a Kubernetes environment.

## Repository Structure

- `argocd-appprojects`
    ArgoCD `AppProject` resources for separation of concerns

- `argocd-apps/`
    ArgoCD `Application` manifests

- `argocd-install/`
    Values file for use when initializing (bootstrapping) and updating ArgoCD core configurations

- `extra-manifests/`
    Raw Kubernetes manifests refernced by ArgoCD `Applications` but not included directly.

## Manual Secrets Required

Some secrets must be created manually for a successful deployment:

1. **Cloudflare API Token Secret**
     - Namespace: `cert-manager`
     - Purpose: Used by the `ClusterIssuer` DNS solver for certificate management.
     - Action: Create a Kubernetes secret containing your Cloudflare API token.

2. **Dex GitHub Client Secret**
     - Secret key: `dex.github.clientSecret`
     - Location: Add manually to the `argocd-secret` in the ArgoCD namespace.
     - Purpose: Enables GitHub OAuth authentication via Dex.

> **Note:** These secrets are not included in this repository for security reasons. Please refer to the documentation in `docs/` for instructions on how to create them.

## Bootstrapping ArgoCD with Helm

To install ArgoCD, use the [Helm](https://helm.sh/) package manager with the provided `values-override.yaml` file in the `argocd-install/` directory. This file customizes the ArgoCD installation to match your environment.

Example command:

```sh
helm repo add argo https://argoproj.github.io/argo-helm
helm upgrade --install argocd argo/argo-cd \
    --namespace argocd --create-namespace \
    -f argocd-install/values-override.yaml
```

Refer to the [official Helm chart documentation](https://github.com/argoproj/argo-helm/tree/main/charts/argo-cd) for additional configuration options.
