# Networking in Kubernetes

## Introduction
Networking is critical for Kubernetes applications to communicate within and outside clusters. This **NerdNest** guide covers Kubernetes networking, essential for cloud and edge computing, aligning with your IT networking knowledge.

## Kubernetes Networking Model
- **Pod-to-Pod**: Each pod gets a unique IP; containers within a pod share localhost.
- **Cluster Networking**: Pods communicate across nodes without NAT.
- **External Access**: Services expose pods to external traffic.

## Key Networking Components
1. **Service**: Abstracts pod IPs for load balancing.
   - **Types**: ClusterIP (internal), NodePort (external), LoadBalancer (cloud).
   - Example:
     ```yaml
     apiVersion: v1
     kind: Service
     metadata:
       name: my-app-lb
     spec:
       selector:
         app: my-app
       ports:
       - port: 80
         targetPort: 80
       type: LoadBalancer
     ```

2. **Ingress**: Manages HTTP/HTTPS traffic with rules:
   ```yaml
   apiVersion: networking.k8s.io/v1
   kind: Ingress
   metadata:
     name: my-ingress
   spec:
     rules:
     - host: example.com
       http:
         paths:
         - path: /
           pathType: Prefix
           backend:
             service:
               name: my-app-service
               port:
                 number: 80
   ```

3. **Network Policies**: Control traffic flow (e.g., restrict pod access).

## Tutorial: Expose an App with Ingress
1. Deploy an app (use previous Deployment example).
2. Create a Service (my-app-service.yaml).
3. Create an Ingress (my-ingress.yaml) as above.
4. Apply:

   ```bash
   kubectl apply -f my-ingress.yaml
   ```

5. Test:
   ```bash
   kubectl get ingress
   ```

## Edge Computing Context
- **MEC (Multi-Access Edge Computing)**: Services enable low-latency edge apps.
- **Network Policies**: Secure IoT device communication in edge clusters.

## Resources
- **Official Docs**: [Kubernetes Networking](https://kubernetes.io/docs/concepts/services-networking/)
- **Free Lab**: [Cilium’s Kubernetes Networking](https://cilium.io/learn/)
- **Book**: “Kubernetes Networking” (O’Reilly, ~€25)
- **X Community**: Follow #KubeNetworking

## Next Steps
Explore [Storage in Kubernetes](storage_in_kubernetes.md) for persistent data. Share networking configs in **NerdNest**!

---
