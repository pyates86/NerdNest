# Key Kubernetes Concepts

## Introduction
Kubernetes uses objects to define and manage applications. This **NerdNest** guide explores key Kubernetes concepts like Deployments, Services, and ConfigMaps, essential for building scalable systems. These align with your IT expertise and are critical for roles in cloud and edge computing.

## Core Kubernetes Objects
1. **Deployment**: Manages pod replicas for scalability and updates.

   ```yaml
   apiVersion: apps/v1
   kind: Deployment
   metadata:
     name: my-app
   spec:
     replicas: 3
     selector:
       matchLabels:
         app: my-app
     template:
       metadata:
         labels:
           app: my-app
       spec:
         containers:
         - name: nginx
           image: nginx:latest
    ```

2. **Service**: Abstracts pod networking, enabling load balancing and discovery.

   ```yaml
   apiVersion: v1
   kind: Service
   metadata:
     name: my-app-service
   spec:
     selector:
       app: my-app
     ports:
     - protocol: TCP
       port: 80
       targetPort: 80
     type: ClusterIP
   ```

3. **ConfigMap**: Stores configuration data (e.g., environment variables).

   ```yaml
   apiVersion: v1
   kind: ConfigMap
   metadata:
     name: my-config
   data:
     db_host: mysql.example.com
   ```

4. **Secret**: Manages sensitive data (e.g., passwords).
5. **Namespace**: Isolates resources for multi-tenancy.

## Applying Objects
Use kubectl apply to create objects. Example:

   ```bash
   kubectl apply -f my-app-deployment.yaml
   kubectl get deployments
   ```

## Tutorial: Deploy a Scalable App
1. Create a Deployment (my-app-deployment.yaml) as above.
2. Create a Service (my-app-service.yaml).
3. Apply both:

   ```bash
   kubectl apply -f my-app-deployment.yaml
   kubectl apply -f my-app-service.yaml
   ```

4. Verify:
   ```bash
   kubectl get pods,services
   ```
5. Scale:

   ```bash 
   kubectl scale deployment my-app --replicas=5
   ```

## Relevance to Edge Computing
- **Deployments**: Scale edge apps (e.g., IoT analytics) dynamically.
- **Services**: Enable low-latency communication in edge clusters.
- **ConfigMaps**: Manage edge device configurations.

## Resources
- **Official Docs**: [Kubernetes Objects](https://kubernetes.io/docs/concepts/overview/working-with-objects/)
- **Free Course**: edX’s “Kubernetes for Developers” (audit free)
- **Tool**: Use Lens for visual Kubernetes management
- **X Updates**: Follow @CNCF for object tips

## Next Steps
Learn about [Setting Up and Managing Kubernetes Clusters](setting_up_and_managing_clusters.md) to create your own cluster. Contribute YAML examples to **NerdNest**!

---
