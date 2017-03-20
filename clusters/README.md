<figure>
<img src="http://www.hypergrid.com/wp-content/themes/hypergrid/img/logo.png" alt="" />
</figure>

Clusters
===========================

Servers across hybrid clouds or local development machines can be associated with a cluster, which is a logical mapping of infrastructure. A user can create a cluster by navigating to **Clusters** page and then clicking on the **+New** button. A user can select from the available networks for clusters.
-   Compute Group (Non-Docker) - for provisioning VMs only (i.e. without Docker)
-   Docker - for setting up container networking on the same host
-   Weave - for setting up container network across multiple hosts
-   Docker Swarm - for setting up container network across multiple hosts
-   Docker UCP - for automating the provisioning of Docker Universal Control Plane nodes

The Advanced Configuration menu can be expanded to provide more advanced options for Container Clusters.
-   **Trusted Blueprints** -- these are the Docker Compose templates that can be deployed on this Cluser. For example, if a cluster owner wishes to restrict users to deploying Wordpress only, then users will not be able to deploy any other application to this cluster.
-   **Trusted Plugins** -- these are the Plug-ins that can be executed on Cluser. For example, if a cluster owner wishes to restrict users to invoking only IT-blessed plug-ins as part of the application deployment or post-provision, then users will not be able to invoke their own plug-ins in this cluster.
-   **Cap-Add Policy** -- the Cluster owner can control container runtime privileges by applying a mandatory approval workflow on container privileges like cap-add and privileged in order to control containers requiring access to all devices on the host or the ability to add Linux capabilities. More information can be found in this blog.
-   **Network Isolation Policy** -- the Cluster owner can provide default network security by creating new isolated networks for new application deployments that do not have pre-configured networks. This eliminates the threat of external attacks that take advantage of network vulnerabilities. More information can be found in this [blog](http://hypergrid.com/hypercloud-delivers-5-layers-of-security-for-your-containerized-applications/).
-   **Max CPU Policy** -- the Cluster owner can specify the maximum amount of CPU that containers can consume within the cluster.
-   **Max Memory Policy** -- the Cluster owner can specify the maximum amount of Memory that containers can consume within the cluster.
-   **VM Termination Protection** -- To prevent the risk of accidentally deleting VMs, the VM termination protection policy can be enabled. If Active, then the Cluster owner would need to approve any request to destory VMs.
-   **Approval Policy** - this option allows the Cluster owner to control whehther approvals are needed for any application deployment request using this cluster. If active, then an approval request will show up under Notifications page for every Docker application request. If inactive, then application deployment requests are approved by default based on the entitlement and quota policies defined in the cluster.
-   **Max Container Policy** -- the Cluster owner can specify the maximum number of containers that users can run within the cluster. Important -- this is a limitation per user, not for the entire cluster.
-   **App Lease** – the Cluster owner can specify the default lease (or maximum amount of time) that applications can run on this cluster. A lease extension can be requested by the user once an application is deployed by selecting Lease from the Actions menu of a deployed application.
-   **Volume Provider** -- this is the default volume provider that will be used when creating and mounting volumes for containers. With this setting, users would not need to provide the volume provider information in the application template. Volume Providers can be registered in the [Cloud Providers](https://github.com/hypergrid-inc/documentation/edit/master/cloud-providers) section.
-   **Entitled Users** -- these are the users who are allowed to deploy container applications to this Cluster. The entitled users do not have permission to manage or delete this cluster. For example, a developer may register his/her local machine and mark it as private. A tenant admin, on the other hand, may share a cluster with a specific group of users or with all tenant users.

**Next Steps**:
-   Provision VMs or register already running servers from the [**Virtual Machines**](https://github.com/hypergrid-inc/documentation/tree/master/virtual-machines) page
