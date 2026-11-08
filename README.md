# taskflow-gitops

Kubernetes manifests for Taskflow. This repo is the single source of truth for what runs in the cluster: ArgoCD watches it and syncs any change.

Part of a three-repo GitOps pipeline:

- `taskflow-infra` builds the EKS cluster.
- `taskflow-app` builds the image; its CI pipeline commits the new image tag here.
- `taskflow-gitops` (this repo) is what ArgoCD deploys.

Layout:

- `manifest/` holds the Deployment and Service.
- `argocd/` holds the ArgoCD Application definition.
