<figure>
<img src="http://www.hypergrid.com/wp-content/themes/hypergrid/img/logo.png" alt="" />
</figure>

HyperCloud - Block Storage Provider Registration
===========================

##   Register a Provider for HyperCloud Block Storage Service

You can now register a Provider for HyperCloud Block Storage Service by navigating to **Cloud Providers** and then clicking on the **+New** button to select **HyperCloud (HBS)**. The required fields are:
-   **Name** -- A name for the HyperCloud end-point
-   **Driver** -- The value here should be **hypergrid/hypercloud:2.0**

The Advanced Configuration menu can be expended to provide more advanced options.
-   **Trusted Blueprints** -- these are the Volume Compose templates that can be used with this cloud provider. For example, if a Tenant Admin wishes to restrict users to provisioning 4GB volumes, then users will not be able to use this block storage provider to provision any other volume.
-   **Approval Enforced** - this toggle allows the Volume Provider owner to control whehther approvals are needed for any provisioning request using this provider. If enabled, then an approval request will show up under Notifications page for every provisioning request. If disabled, then provisioning requests are approved by default based on the entitlement and quota policies defined in the Cloud Provider.
-   **Default Size** -- this is the default size (in GB) of the disk (or volume) provisioned. An acceptepted value is **size=2** - where 2 is value in GB
-   **Max Size** -- this is the maximum size (in GB) of the disk (or volume) that can be provisioned. An acceptepted value is **100** - where 100 is value in GB
-   **Opts (Secure)** -- this is the password to the HyperCloud proxy. An accepted value is **HBS_PASSWORD=HyperGrid123**
-   **Opts** -- these are the parameters needed to connect to the HyperCloud proxy. The required parameters are:
    * **HBS_CSV** -- this is the location of the Cluster Shared Volume (CSV) (e.g. HBS_CSV=C:\ClusterStorage\Volume1)
    * **HBS_ENDPOINT** -- this is the HyperCloud Proxy end-point (e.g. HBS_ENDPOINT=https://10.100.246.20)
    * **HBS_PASSWORD** -- this is the password for the HyperCloud Proxy (e.g. HBS_PASSWORD=HyperGrid123)
-   **Volume Limit  (GB)** -- this is the total limit on all volumes (in GB). An accepted value **1000** - where 1,000 is in GB
-   **Volume Type** -- this is the type of volume provisioned - e.g. SSD or Non-SSD
-   **Volume IOPS** -- this is the expected IOPS from the registered storage provider
-   **Lease** - this is the lease (or the maximum amount of time) for provisioned volumes. If a lease expires, then the provisioned volume will be automatically destroyed. Users can request a lease extension from the Volumes page.
-   **Quota Policies** -- these are pre-defined policies for setting quotas on the number of volumes. Multiple quota policies can be selected to customize controls per user or per group of users.

The optional fields allow you to enforce granular access controls and associate this provider with a quota policy.
-   **Entitled Users** -- these are the users who are allowed to use this Volume Provider for volume provisioning. The entitled users do not have permission to manage or delete this cloud provider and will not be able to view any of the credentials.

Once saved, a user can test the connection by clicking on **Test Connection** button.

##   Next Steps

-   [**Provision a Volume and Attach to a Running VM**](https://github.com/hypergrid-inc/documentation/tree/master/volumes)
