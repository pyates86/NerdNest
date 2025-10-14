# Storage Management in OpenShift

## Introduction
OpenShift provides robust storage options for stateful applications. This **NerdNest** guide covers storage mechanisms, vital for cloud and edge computing, leveraging your IT systems knowledge.

## Storage Concepts
1. **Persistent Volume (PV)**: Cluster-wide storage (e.g., NFS, cloud).
2. **Persistent Volume Claim (PVC)**: Requests storage for pods.

   ```yaml
   apiVersion: v1
   kind: PersistentVolumeClaim
   metadata:
     name: mysql-pvc
   spec:
     storageClassName: standard
     accessModes:
     - ReadWriteOnce
     resources:
       requests:
         storage: 10Gi
   ```

3. **StorageClass**: Enables dynamic provisioning.

   ```yaml
   apiVersion: storage.k8s.io/v1
   kind: StorageClass
   metadata:
     name: standard
   provisioner: kubernetes.io/aws-ebs
   parameters:
     type: gp3
   ```

## Tutorial: Create a PVC
1. Create a PVC (mysql-pvc.yaml).
2. Update an app to use PVC:

   ```yaml
   spec:
     containers:
     - name: mysql
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
   oc apply -f mysql-pvc.yaml
   oc apply -f mysql-app.yaml
   ```

## Edge Computing Relevance
- **Local Storage**: Supports edge devices with limited connectivity.
- **Dynamic Provisioning**: Simplifies IoT storage needs.

## Resources
- **Official Docs**: [OpenShift Storage](https://docs.openshift.com/container-platform/4.13/storage/)
- **Free Course**: Red Hat’s “OpenShift Storage Basics” (free via Developer Sandbox)
- **Tool**: OpenShift Data Foundation
- **X Community**: Follow #OpenShiftStorage

## Next Steps
Learn [CI/CD and DevOps with OpenShift](cicd_and_devops_with_openshift.md) for automated deployments. Contribute storage examples to **NerdNest**!

---
