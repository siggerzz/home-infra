# 🏠 home-infra

<div align="center">
  <p><em>My home infrastructure managed through GitOps using Flux and Talos Linux</em></p>
</div>

## 📂 Repository Structure

```
├── .github/           # GitHub workflows and settings
├── .taskfiles/        # Task runner configurations
├── kubernetes/        # Kubernetes manifests
│   ├── apps/          # Application deployments
│   ├── bootstrap/     # Initial cluster bootstrap configurations
│   └── flux/          # Flux system configurations and repositories
```

## 🎮 Cluster Overview

This repository contains the configuration for my home Kubernetes cluster. The cluster is provisioned using [Talos Linux](https://www.talos.dev/) and follows the GitOps methodology using [Flux](https://fluxcd.io/).

### 💻 Cluster Hardware

| Hostname   | Node Type     | Hardware          | CPU      | Memory | Storage   |
| ---------- | ------------- | ----------------- | -------- | ------ | --------- |
| glados-c01 | Control Plane | Lenovo M720q Tiny | i5-8400T | 16GB   | 256GB SSD |
| glados-w01 | Worker        | Lenovo M720q Tiny | i5-8400T | 16GB   | 256GB SSD |
| glados-w02 | Worker        | Lenovo M720q Tiny | i5-8400T | 16GB   | 256GB SSD |

### 🔧 Core Components

- **🌐 Container Network Interface (CNI)**: [Cilium](https://github.com/cilium/cilium)
- **🔐 Certificate Management**: [cert-manager](https://github.com/cert-manager/cert-manager)
- **💾 Storage**: [OpenEBS](https://github.com/openebs/openebs)
- **🚦 Ingress Controller**: [ingress-nginx](https://github.com/kubernetes/ingress-nginx)

### 🌐 Networking Stack

- **📡 DNS**:
  - External DNS management via [external-dns](https://github.com/kubernetes-sigs/external-dns)
  - Internal DNS via [k8s-gateway](https://github.com/ori-edge/k8s_gateway)
- **🔒 Tunnel**: [Cloudflare Tunnel](https://github.com/cloudflare/cloudflared)

### 🚀 GitOps

The cluster is managed using Flux, which automatically reconciles the cluster state with the declarations in this repository. Key aspects include:

- ⏱️ Automated reconciliation every 30 minutes
- 🔑 Secrets management using [SOPS](https://github.com/getsops/sops)
- 🔄 Automated dependency updates via [Renovate](https://github.com/renovatebot/renovate)

### 📱 Applications

Currently deployed applications:

- 🎬 Jellyfin - Media Server
- 🔄 Echo Server - Testing HTTP/HTTPS requests

## 🛠️ Tools & Technologies

### Core Infrastructure

- 🖥️ [Talos](https://www.talos.dev/) - Operating system for Kubernetes
- 🔄 [Flux](https://fluxcd.io/) - GitOps operator for Kubernetes
- 📦 [Helm](https://helm.sh/) - Package manager for Kubernetes
- 📄 [Helmfile](https://helmfile.readthedocs.io/) - Declarative spec for deploying Helm charts
- ⚡ [Kubectl](https://kubernetes.io/docs/reference/kubectl/) - Kubernetes command-line tool

### Security & Secrets

- 🔐 [SOPS](https://github.com/getsops/sops) - Secrets encryption
- 🔒 [Age](https://github.com/FiloSottile/age) - File encryption tool

## 🙏 Acknowledgments

This cluster setup is inspired by and based on the [onedr0p/cluster-template](https://github.com/onedr0p/cluster-template).
