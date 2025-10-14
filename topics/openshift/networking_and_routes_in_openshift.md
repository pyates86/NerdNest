# Networking and Routes in OpenShift

## Introduction
Networking in OpenShift enables app communication and external access. This **NerdNest** guide covers OpenShift’s networking model and Routes, essential for cloud and edge computing.

## Networking Model
- **Pod-to-Pod**: Inherits Kubernetes model with unique pod IPs.
- **Cluster Networking**: Uses OpenShift SDN for connectivity.
- **External Access**: Routes provide domain-based access.

## Key Components
1. **Service**: Abstracts pod IPs for load balancing.

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
       port: 8080
       targetPort: 8080
   ```

2. **Route**: Exposes services externally.

   ```yaml
   apiVersion: route.openshift.io/v1
   kind: Route
   metadata:
     name: my-app-route
   spec:
     to:
       kind: Service
       name: my-app-service
     port:
       targetPort: 8080
   ```

3. **Network Policies**: Control traffic, similar to Kubernetes.

## Tutorial: Expose an App with a Route
1. Deploy an app (use previous S2I example).
2. Create a Service (my-app-service.yaml).
3. Create a Route (my-app-route.yaml).
4. Apply:

   ```bash
   oc apply -f my-app-service.yaml
   oc apply -f my-app-route.yaml
   ```

5. Test:
   
   ```bash
   oc get routes
   ```

## Edge Computing Context
- **Routes**: Enable low-latency access for edge apps.
- **Network Policies**: Secure IoT device communication.

## Resources
- **Official Docs**: [OpenShift Networking](https://docs.openshift.com/container-platform/4.13/networking/)
- **Free Lab**: Red Hat Developer Sandbox
- **Book**: “OpenShift Networking” (O’Reilly, ~€25)
- **X Community**: Follow #OpenShiftNetworking

## Next Steps
Explore [Storage Management in OpenShift](storage_management_in_openshift.md) for persistent data. Share networking configs in **NerdNest**!

---
