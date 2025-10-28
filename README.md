> [!CAUTION]
> ## Community Charts – Not Officially Supported
> This repository is maintained by the community and is **not** officially supported by OpenCloud GmbH.  
>  
> For **production-ready Helm charts** designed for **mission-critical** workloads, please use the enterprise offering, available with a [business subscription](https://opencloud.eu/en/product/service-and-support).  
>  
> To access **production-ready helm charts** get in touch with us via [contact form](https://opencloud.eu/en/contact-us) or Email [sales@opencloud.eu](mailto:sales@opencloud.eu).

# Community Helm Charts

Welcome to the **OpenCloud Helm Charts** repository! This repository is intended as a community-driven space for developing and maintaining Helm charts for deploying OpenCloud on Kubernetes.
**Community Maintained** This repository is **community-maintained** and **not officially supported by OpenCloud GmbH**. Use at your own risk, and feel free to contribute to improve the project!

## 📑 Table of Contents

- [About](#-about)
- [Community](#-community)
- [Contributing](#-contributing)
- [Prerequisites](#prerequisites)
- [Version Stability Notice](#⚠️-version-stability-notice)
- [Available Charts](#-available-charts)
  - [Production Chart](#production-chart-chartsopencloud)
  - [Microservices Chart](#microservices-chart-chartsopencloud-microservices)
  - [Development Chart](#development-chart-chartsopencloud-dev)
- [License](#-license)
- [Community Maintained](#community-maintained)

## 🚀 About

This repository is created to **welcome contributions from the community**. It does not contain official charts from OpenCloud GmbH and is **not officially supported by OpenCloud GmbH**. Instead, these charts are maintained by the open-source community.

OpenCloud is a cloud collaboration platform that provides file sync and share, document collaboration, and more. This Helm chart deploys OpenCloud with Keycloak for authentication, MinIO for object storage, and multiple options for document editing including Collabora and OnlyOffice.

## 💬 Community

Join our Matrix chat for discussions about OpenCloud Helm Charts:
- [OpenCloud Helm on Matrix](https://matrix.to/#/%23opencloud-helm:matrix.org)

For general OpenCloud discussions:
- [OpenCloud on Matrix](https://matrix.to/#/%23opencloud:matrix.org)
- [OpenCloud on Mastodon](https://social.opencloud.eu/@OpenCloud)
- [GitHub Discussions](https://github.com/orgs/opencloud-eu/discussions)

## 💡 Contributing

We encourage contributions from the community! This repository follows a community-driven development model with defined roles and responsibilities.

For detailed contribution guidelines, please see our [CONTRIBUTING.md](./CONTRIBUTING.md) document.

This includes:
- How to submit contributions
- Our community governance model
- How to become a reviewer or maintainer

The current maintainers and reviewers are listed in [MAINTAINERS.md](./MAINTAINERS.md).

## Prerequisites

- Kubernetes 1.19+
- Helm 3.2.0+
- PV provisioner support in the underlying infrastructure (if persistence is enabled)
- External ingress controller (e.g., Cilium Gateway API) for routing traffic to the services

## ⚠️ Version Stability Notice

**Important**: These Helm charts are currently at version `0.x.x`, which according to [Semantic Versioning 2.0](https://semver.org/spec/v2.0.0.html#spec-item-4) means:
- The charts are still under heavy development
- Breaking changes may occur at any time
- The public API should not be considered stable
- Use with caution in production environments

We recommend pinning to specific chart versions and thoroughly testing updates before applying them.

## 📦 Available Charts

This repository contains the following charts:

### Production Chart (`charts/opencloud`)

The complete OpenCloud deployment with all components for production use:

- Full microservices architecture
- Keycloak for authentication
- MinIO for object storage
- Document editing with Collabora and/or OnlyOffice
- Full Gateway API integration

[View Production Chart Documentation](./charts/opencloud/README.md)

### Microservices Chart (`charts/opencloud-microservices`)

**Architecture**: Pod-per-service
- Every single service in its own pod
- Full Gateway API integration
- NATS service discovery required
- Keycloak for authentication
- MinIO for object storage
- Integrated OpenLDAP 
- Integrated ClamAV
- Posix support
- Helm and Timoni Chart for FluxCD
- Document editing with Collabora and/or OnlyOffice
- Slightly higher resource usage due to microservices pod overhead
- See [architectural warnings](./charts/opencloud-microservices/README.md#architectural-considerations)

### Development Chart (`charts/opencloud-dev`)

A lightweight single-container deployment for development and testing:

- Simplified deployment (single Docker container)
- Minimal resource requirements
- Quick setup for testing

[View Development Chart Documentation](./charts/opencloud-dev/README.md)

## 📜 License

This project is licensed under the **AGPLv3** license. See the [LICENSE](LICENSE) file for more details.


