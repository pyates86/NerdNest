# CI/CD and DevOps with Kubernetes

## Introduction
Kubernetes enhances CI/CD pipelines, a core DevOps practice, by automating deployments. This **NerdNest** guide explores integrating Kubernetes with CI/CD tools, aligning with your IT experience and edge computing interests.

## CI/CD in Kubernetes
- **Continuous Integration (CI)**: Build/test code (e.g., Jenkins, GitLab CI).
- **Continuous Delivery/Deployment (CD)**: Automate app updates in Kubernetes.
- **GitOps**: Use Git as the source of truth for declarative deployments.

## Key Tools
1. **Jenkins**: Runs CI/CD pipelines with Kubernetes plugins.
2. **GitLab CI**: Integrated pipelines for Kubernetes deployments.
3. **ArgoCD**: GitOps tool for continuous deployment.

   ```yaml
   apiVersion: argoproj.io/v1alpha1
   kind: Application
   metadata:
     name: my-app
   spec:
     source:
       repoURL: https://github.com/your-repo/my-app.git
       path: manifests
     destination:
       server: https://kubernetes.default.svc
       namespace: default
   ```

## Tutorial: Set Up a GitLab CI Pipeline
1. Create a .gitlab-ci.yml:
   
   ```yaml
   stages:
     - build
     - deploy
   build:
     stage: build
     script:
       - docker build -t my-app:latest .
       - docker push my-app:latest
   deploy:
     stage: deploy
     script:
       - kubectl apply -f k8s/deployment.yaml
   ```

2. Push to GitLab and verify pipeline execution.
3. Deploy to Kubernetes cluster:

   ```bash
   kubectl get deployments
   ```

## Edge Computing Context
- **GitOps for Edge**: Automate edge cluster updates with ArgoCD.
- **Lightweight Pipelines**: Optimize for resource-constrained edge devices.

## Resources
- **Official Docs**: [Kubernetes CI/CD](https://kubernetes.io/docs/tasks/)
- **Free Course**: Coursera’s “CI/CD for Kubernetes” (audit free)
- **Tool**: Flux for GitOps
- **X Community**: Follow #GitOps

## Next Steps
Explore [Security and Best Practices in Kubernetes](security_and_best_practices.md) for secure deployments. Share CI/CD pipelines in **NerdNest**!

---
