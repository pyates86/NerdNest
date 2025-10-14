# Key OpenShift Concepts

## Introduction
OpenShift uses Kubernetes objects enhanced with enterprise features. This **NerdNest** guide covers key concepts like Projects, Routes, and BuildConfigs, essential for building scalable apps with your IT expertise.

## Core OpenShift Objects
1. **Project**: Logical group for resources, isolating apps.

   ```yaml
   apiVersion: project.openshift.io/v1
   kind: Project
   metadata:
     name: my-project
   ```

2. **Route**: Exposes services to external traffic.

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

3. **BuildConfig**: Defines how to build container images.

   ```yaml
   apiVersion: build.openshift.io/v1
   kind: BuildConfig
   metadata:
     name: my-app-build
   spec:
     source:
       git:
         uri: https://github.com/your-repo/my-app.git
     output:
       to:
         kind: ImageStreamTag
         name: my-app:latest
     strategy:
       type: Source
   ```

4. **DeploymentConfig**: Manages app deployments, similar to Kubernetes Deployments.
5. **ImageStream**: Tracks container image versions.

## Applying Objects
Use `oc apply` to create objects. Example:

   ```bash
   oc apply -f my-project.yaml
   oc get projects
   ```

## Tutorial: Create a Project and Route
1. Create a Project (my-project.yaml).
2. Create a Route (my-route.yaml).
3. Apply both:

   ```bash
   oc apply -f my-project.yaml
   oc apply -f my-route.yaml
   ```

4. Verify:

   ```bash
   oc get routes
   ```

5. Test the Route URL in a browser.

## Relevance to Edge Computing
- **Projects**: Isolate edge app resources.
- **Routes**: Enable low-latency access for edge devices.
- **BuildConfigs**: Automate image builds for edge deployments.

## Resources
- **Official Docs**: [OpenShift Objects](https://docs.openshift.com/container-platform/4.13/applications/)
- **Free Course**: Red Hat’s “OpenShift for Developers” (free via Developer Sandbox)
- **Tool**: OpenShift Web Console for visual management
- **X Updates**: Follow @RedHat for object tips

## Next Steps
Learn about [Setting Up an OpenShift Cluster](setting_up_an_openshift_cluster.md) to create your own cluster. Contribute examples to **NerdNest**!

---
