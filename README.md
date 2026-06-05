# AKS Capstone GitOps Repository

This repository is the GitOps source of truth for the Enterprise AKS DevOps / DevSecOps / Platform Engineering Capstone.

## Purpose

This repo stores Kubernetes desired state for the capstone platform and application workloads.

Argo CD watches this repository and syncs the desired state into the AKS cluster.

## Related repositories

### Platform repo

terraform-azure-aks

Purpose:

- Azure infrastructure
- AKS platform provisioning
- Platform tools installation guides
- Capstone Sinhala/English guides

### Application repo

aks-capstone-store-app

Purpose:

- Application source code
- Dockerfiles
- GitHub Actions CI
- SonarCloud quality checks
- Trivy image scanning
- Container image build and push to ACR

### GitOps repo

aks-capstone-gitops

Purpose:

- Kubernetes manifests
- Environment overlays
- Argo CD Applications
- Gateway routes
- Desired state for dev, qa, and prod

## Environment model

The AKS cluster is shared for cost control.

Application environments are represented as Kubernetes namespaces:

- capstone-dev
- capstone-qa
- capstone-prod

## GitOps principle

Git is the source of truth.

Manual cluster changes should be avoided.

Changes should flow through:

Pull Request
→ Review
→ Merge
→ Argo CD sync
→ Kubernetes cluster update
