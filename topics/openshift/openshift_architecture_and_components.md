# OpenShift Architecture and Components

## Introduction
OpenShift builds on Kubernetes to deliver an enterprise-grade container platform. This **NerdNest** guide explores OpenShift’s architecture and components, aligning with your IT expertise for cloud and edge computing roles.

## OpenShift Architecture
OpenShift extends Kubernetes with additional layers for developer productivity and enterprise reliability. It consists of a control plane and worker nodes, enhanced by Red Hat-specific features.

### Core Components
1. **Kubernetes Core**: Inherits pods, nodes, and control plane (e.g., kube-apiserver, etcd).
2. **OpenShift Enhancements**:
   - **Web Console**: GUI for managing clusters and apps.
   - **oc CLI**: Command-line tool for OpenShift operations.
   - **OperatorHub**: Marketplace for installing Operators.
   - **Source-to-Image (S2I)**: Automates container image builds.
3. **Cluster Services**: Includes monitoring (Prometheus), logging, and registry.

### Master vs. Worker Nodes
- **Master Nodes**: Run control plane and OpenShift-specific services.
- **Worker Nodes**: Execute application workloads via pods.

## Key Features
- **Projects**: Logical groups for apps, replacing Kubernetes Namespaces.
- **Routes**: Expose services to external traffic, similar to Ingress.
- **BuildConfigs**: Define build processes for app deployment.

## Practical Tutorial: Explore Cluster Components
1. Log in to an OpenShift cluster:

   ```bash
   oc login --token=<your-token> --server=<your-cluster-api>
   ```

2. Check nodes:

   ```bash
   oc get nodes
   ```

3. View cluster services:

   ```bash
   oc get services
   ```

Output: Displays nodes and services.

## Why It Matters
Understanding OpenShift’s architecture is crucial for:
- **Enterprise Deployments**: Managing apps on AWS or Azure with OpenShift.
- **Edge Computing**: Deploying lightweight pods on edge devices.
- **Career Skills**: Foundation for DevOps roles (€100k+ in Ireland).

## Resources
- **Official Docs**: [OpenShift Architecture](https://docs.openshift.com/container-platform/4.13/architecture/)
- **Free Lab**: Red Hat Developer Sandbox (free tier)
- **Book**: “OpenShift in Action” by Jamie Duncan (~€30)
- **X Community**: Follow #OpenShift for tips

## Next Steps
Dive into [Key OpenShift Concepts](key_openshift_concepts.md) to explore Projects and Routes. Share your cluster insights in **NerdNest**!

---
