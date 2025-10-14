# Kubernetes Fundamentals

## Introduction
Kubernetes orchestrates containers across clusters, automating deployment, scaling, and management. This **NerdNest** guide covers the fundamental components and architecture of Kubernetes, building a foundation for IT learners. With your IT background, these concepts align with your systems knowledge and prepare you for cloud and edge computing roles.

## Kubernetes Architecture
Kubernetes operates on a cluster—a set of nodes (servers) managed by a control plane. Nodes run containerized applications, while the control plane coordinates tasks.

### Core Components
1. **Pod**: Smallest deployable unit, hosting one or more containers that share storage/network.
2. **Node**: A worker machine (physical or virtual) running pods. Includes:
   - **Kubelet**: Agent managing pods on a node.
   - **Container Runtime**: Software (e.g., Docker, containerd) running containers.
3. **Cluster**: Collection of nodes managed by the control plane.
4. **Control Plane**: Manages the cluster, including:
   - **kube-apiserver**: Handles API requests.
   - **etcd**: Distributed key-value store for cluster data.
   - **kube-scheduler**: Assigns pods to nodes.
   - **kube-controller-manager**: Runs controllers (e.g., ReplicaSet).
   - **cloud-controller-manager**: Integrates with cloud providers (e.g., AWS, Azure).

### Master vs. Worker Nodes
- **Master Nodes**: Run the control plane components.
- **Worker Nodes**: Run application pods, managed by kubelet.

## Pods in Depth
Pods encapsulate containers, sharing a network namespace (same IP/port) and storage volumes. Example pod definition:

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: my-app
spec:
  containers:
  - name: my-app-container
    image: nginx:latest
```

Deploy with:

```bash
kubectl apply -f my-app.yaml
```

## Key Concepts
- **Labels**: Key-value pairs for organizing resources (e.g., app=frontend).
- **Selectors**: Match labels to filter resources (e.g., for Services).
- **Namespaces**: Virtual clusters for resource isolation (e.g., dev, prod).

## Practical Tutorial: Deploy a Simple Pod
1. Install kubectl:

```bash
sudo snap install kubectl --classic
```

2. Create a pod YAML file (my-app.yaml) as above.
3. Deploy:

```bash
kubectl apply -f my-app.yaml
```

4. Check status:

```bash
kubectl get pods
```

Output: Shows my-app as Running.

## Why It Matters
Understanding these fundamentals is crucial for:
- **Cloud Deployments**: Managing apps on AWS EKS or Azure AKS.
- **Edge Computing**: Deploying lightweight pods on edge devices with KubeEdge.
- **Career Skills**: Core knowledge for DevOps roles (€100k+ in Ireland).

## Resources
- **Official Docs**: [Kubernetes Concepts](https://kubernetes.io/docs/concepts/)
- **Free Lab**: [Katacoda Kubernetes Playground](https://www.katacoda.com/courses/kubernetes)
- **Book**: “Kubernetes in Action” by Marko Lukša (~€30)
- **X Community**: Follow #Kubernetes for tips

## Next Steps
Dive into [Key Kubernetes Concepts](key_kubernetes_concepts.md) to explore Deployments, Services, and more. Share your pod experiments in **NerdNest**!

---
