# Setting Up an OpenShift Cluster

## Introduction
An OpenShift cluster is the foundation for running containerized applications. This **NerdNest** guide covers setting up and managing clusters, aligning with your IT experience for cloud and edge computing roles.

## Cluster Setup Options
1. **Local Clusters**:
   - **Minishift**: Single-node cluster for learning.
   - **CodeReady Containers (CRC)**: Developer-focused local cluster.
2. **Cloud Providers**:
   - Red Hat OpenShift on AWS (ROSA)
   - Azure Red Hat OpenShift
   - OpenShift Dedicated (Google Cloud)
3. **On-Premises**: Use OpenShift Container Platform.

## Tutorial: Set Up a CodeReady Containers Cluster
1. Install CRC:

   ```bash
   curl -LO https://developers.redhat.com/content-gateway/file/crc-linux-latest-amd64.tar.xz
   tar -xvf crc-linux-latest-amd64.tar.xz
   sudo mv crc /usr/local/bin/
   ```

2. Start cluster:

   ```bash
   crc start
   ```

3. Log in:

   ```bash
   oc login -u kubeadmin -p <password> https://api.crc.testing:6443
   ```

4. Verify:

   ```bash
   oc get nodes
   ```

## Managing Clusters
- **Scaling**: Add nodes via OpenShift Console or CLI.
- **Upgrades**: Use OpenShift’s automated upgrade process.
- **Monitoring**: Leverage built-in Prometheus.

## Edge Computing Context
- **Lightweight Clusters**: CRC for edge development.
- **Hybrid Deployments**: ROSA for edge-cloud integration.

## Resources
- **Official Docs**: [OpenShift Installation](https://docs.openshift.com/container-platform/4.13/installing/)
- **Free Lab**: Red Hat Developer Sandbox (free tier)
- **Book**: “Deploying to OpenShift” by Graham Dumpleton (~€30)
- **X Community**: Follow #OpenShift for cluster tips

## Next Steps
Explore [Deploying Applications on OpenShift](deploying_applications_on_openshift.md) to deploy apps. Share cluster configs in **NerdNest**!

---
