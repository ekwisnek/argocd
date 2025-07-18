# ArgoCD Apps

This folder contains raw ArgoCD application manifests for managing deployments via ArgoCD.

## Structure

- `apps/` - Application manifests and related resources not part of core infrastructure
- `core/` - Application manigests and related resources for core infrastructure
- `README.md` - This documentation

> Note: AppProjects are located in a separate folder.

## Usage

1. Clone the repository.
2. Apply manifests using `kubectl apply -f <file>.yaml`.
3. Access the ArgoCD UI to manage and monitor applications.

## Resources

- [ArgoCD Documentation](https://argo-cd.readthedocs.io/)
- [Getting Started Guide](https://argo-cd.readthedocs.io/en/stable/getting_started/)

## Contributing

Please submit issues or pull requests for improvements or new applications.
