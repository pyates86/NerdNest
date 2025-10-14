# Storage in Kubernetes

## Introduction
Kubernetes provides flexible storage options for stateful applications. This **NerdNest** guide covers storage mechanisms, vital for cloud and edge computing, leveraging your IT systems knowledge.

## Storage Concepts
1. **Persistent Volume (PV)**: Cluster-wide storage resource (e.g., NFS, cloud storage).
2. **Persistent Volume Claim (PVC)**: Request for storage by a pod.
3. **StorageClass**: Defines dynamic storage provisioning.
   ```yaml
   apiVersion: storage.k8s.io/v1
   kind: StorageClass
   metadata:
     name: fast-storage
   provisioner: kubernetes.io/aws-ebs
   parameters:
     type: gp3
   ```

## Tutorial: Create a PVC
1. Create a PVC (mysql-pvc.yaml):

   ```yaml
   apiVersion: v1
   kind: PersistentVolumeClaim
   metadata:
     name: mysql-pvc
   spec:
     storageClassName: fast-storage
     accessModes:
     - ReadWriteOnce
     resources:
       requests:
         storage: 10Gi
   ```

2. Update StatefulSet to use PVC:

   ```yaml
   spec:
     volumeMounts:
     - name: mysql-data
       mountPath: /var/lib/mysql
     volumes:
     - name: mysql-data
       persistentVolumeClaim:
         claimName: mysql-pvc
   ```

3. Apply:

   ```bash
   kubectl apply -f mysql-pvc.yaml
   kubectl apply -f mysql-statefulset.yaml
   ```

## Edge Computing Relevance
- **Local Storage**: Critical for edge devices with limited connectivity.
- **Dynamic Provisioning**: Simplifies storage for IoT workloads.

## Resources
- **Official Docs**: [Kubernetes Storage](https://kubernetes.io/docs/concepts/storage/)
- **Free Course**: Udemy’s “Kubernetes Storage” (~€15)
- **Tool**: Rook for storage orchestration
- **X Community**: Follow #KubeStorage

## Next Steps
Learn [CI/CD and DevOps with Kubernetes](cicd_and_devops.md) for automated deployments. Contribute storage examples to **NerdNest**!

---
