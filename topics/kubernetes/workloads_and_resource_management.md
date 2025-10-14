# Workloads and Resource Management

## Introduction
Kubernetes workloads define how applications run, scale, and recover. This **NerdNest** guide covers workload types and resource management, key for optimizing cloud and edge deployments with your IT expertise.

## Workload Types
1. **Pod**: Basic unit, often managed by higher-level controllers.
2. **ReplicaSet**: Ensures a specified number of pod replicas run.
3. **Deployment**: Manages ReplicaSets for updates and scaling.
4. **StatefulSet**: Handles stateful apps (e.g., databases) with persistent identities.
5. **DaemonSet**: Runs one pod per node (e.g., for logging).
6. **Job/CronJob**: Executes one-time or scheduled tasks.

## Resource Management
- **Resource Limits**: Set CPU/memory constraints:

  ```yaml
  spec:
    containers:
    - name: my-app
      image: nginx
      resources:
        limits:
          cpu: "1"
          memory: "512Mi"
        requests:
          cpu: "0.5"
          memory: "256Mi"
   ```

- **Horizontal Pod Autoscaler (HPA)**: Scales pods based on metrics:

   ```bash
   kubectl autoscale deployment my-app --cpu-percent=80 --min=2 --max=10
   ```

- **Scheduler**: Assigns pods to nodes based on resources and affinity rules.

## Tutorial: Deploy a StatefulSet
1. Create a StatefulSet (mysql-statefulset.yaml):

   ```yaml
   apiVersion: apps/v1
   kind: StatefulSet
   metadata:
     name: mysql
   spec:
     serviceName: mysql
     replicas: 3
     selector:
       matchLabels:
         app: mysql
     template:
       metadata:
         labels:
           app: mysql
       spec:
         containers:
         - name: mysql
           image: mysql:8
           env:
           - name: MYSQL_ROOT_PASSWORD
             value: "password"
   ```

2. Apply:

   ```bash
   kubectl apply -f mysql-statefulset.yaml
   ```

3. Verify:
   
   ```bash
   kubectl get statefulsets
   ```

## Edge Computing Relevance
- **Lightweight Workloads**: Use DaemonSets for edge monitoring.
- **Autoscaling**: Optimize resource usage in edge clusters with limited hardware.

## Resources
- **Official Docs**: [Kubernetes Workloads](https://kubernetes.io/docs/concepts/workloads/)
- **Free Course**: Udemy’s “Kubernetes Workloads” (~€15)
- **Tool**: K9s for CLI-based workload management
- **X Community**: Follow @Kubernetesio for scaling tips

## Next Steps
Learn [Networking in Kubernetes](networking_in_kubernetes.md) to connect your workloads. Contribute workload examples to **NerdNest**!

---
