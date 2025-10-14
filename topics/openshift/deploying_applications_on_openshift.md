# Deploying Applications on OpenShift

## Introduction
OpenShift simplifies app deployment with tools like Source-to-Image (S2I). This **NerdNest** guide covers deploying applications, aligning with your IT expertise for cloud and edge computing.

## Deployment Methods
1. **Source-to-Image (S2I)**: Builds images from source code.
2. **Docker Images**: Deploys pre-built container images.
3. **Templates**: Predefined app configurations.

## Tutorial: Deploy an App with S2I
1. Create a new app from source:

   ```bash
   oc new-app python~https://github.com/your-repo/sample-app.git
   ```

2. Monitor build:

   ```bash
   oc get builds
   ```

3. Expose the app:

   ```bash
   oc expose service/sample-app
   ```

4. Verify:

   ```bash
   oc get routes
   ```

## Edge Computing Relevance
- **S2I**: Automates builds for edge apps.
- **Lightweight Images**: Optimize for edge device constraints.

## Resources
- **Official Docs**: [OpenShift Applications](https://docs.openshift.com/container-platform/4.13/applications/)
- **Free Course**: Red Hat’s “OpenShift App Development” (free via Developer Sandbox)
- **Tool**: OpenShift CLI for app management
- **X Community**: Follow @OpenShift for deployment tips

## Next Steps
Learn [Networking and Routes in OpenShift](networking_and_routes_in_openshift.md) to expose apps. Contribute deployment examples to **NerdNest**!

---
