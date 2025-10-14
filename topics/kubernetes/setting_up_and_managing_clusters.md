# Setting Up and Managing Kubernetes Clusters

## Introduction
A Kubernetes cluster is the foundation for running containerized applications. This **NerdNest** guide covers setting up and managing clusters, from local setups to cloud providers, aligning with your IT experience for cloud and edge computing roles.

## Cluster Setup Options
1. **Local Clusters**:
   - **Minikube**: Single-node cluster for learning.
   - **Kind**: Multi-node clusters in Docker containers.
2. **Cloud Providers**:
   - AWS Elastic Kubernetes Service (EKS)
   - Azure Kubernetes Service (AKS)
   - Google Kubernetes Engine (GKE)
3. **Bare-Metal**: Use kubeadm for custom setups.

## Tutorial: Set Up a Minikube Cluster
1. Install dependencies (e.g., Docker, kubectl):

   ```bash
   sudo snap install docker
   sudo snap install kubectl --classic
   ```

2. Install Minikube:

   ```bash
   curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
   sudo install minikube-linux-amd64 /usr/local/bin/minikube
   ```
3. Start cluster:

   ```bash
   minikube start --driver=docker
   ```

4. Verify:

   ```bash
   kubectl cluster-info
   kubectl get nodes
   ```

## Managing Clusters
- **Scaling Nodes**: Add/remove nodes with cloud provider dashboards or kubeadm.
- **Upgrades**: Use kubeadm upgrade for version updates.
- **Monitoring**: Integrate Prometheus for metrics.

## Edge Computing Context
- **Lightweight Clusters**: Use MicroK8s or KubeEdge for edge devices (e.g., IoT gateways).
- **Cloud Integration**: Hybrid setups with EKS/AKS for edge-cloud data sync.

## Resources
- **Official Docs**: [Kubernetes Setup](https://kubernetes.io/docs/setup/)
- **Free Lab**: [Play with Kubernetes](https://labs.play-with-k8s.com/)
- **Book**: “Kubernetes Up & Running” by Brendan Burns (~€30)
- **X Community**: Follow #KubeCon for cluster tips

## Next Steps
Explore [Workloads and Resource Management](workloads_and_resource_management.md) to deploy apps on your cluster. Share cluster configs in **NerdNest**!

---
