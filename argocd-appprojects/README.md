# ArgoCD AppProjects

This folder contains additional [ArgoCD AppProjects](https://argo-cd.readthedocs.io/en/stable/operator-manual/app_projects/) definitions.

## Purpose

AppProjects help organize and manage access, permissions, and policies for groups of ArgoCD applications.

## Usage

- Place your AppProject YAML manifests in this directory.
- Apply them to your ArgoCD instance using `kubectl apply -f`.

## Resources

- [ArgoCD Documentation: AppProjects](https://argo-cd.readthedocs.io/en/stable/operator-manual/app_projects/)
- [ArgoCD GitHub](https://github.com/argoproj/argo-cd)
