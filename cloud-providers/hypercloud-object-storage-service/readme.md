<figure>
<img src="http://www.hypergrid.com/wp-content/themes/hypergrid/img/logo.png" alt="" />
</figure>

HyperCloud - Object Storage Service Registration
===========================

##   Register a Provider for HyperCloud Object Storage Service

You can now register a Provider for HyperCloud Object Storage Service by navigating to **Cloud Providers** and then clicking on the **+New** button to select **HyperCloud (HOS)**. The required fields are:
-   **Name** -- A name for the HyperCloud object storage end-point
-   **Endpoint URL** -- This is the URL of the running object storage service (e.g. the deployed Minio application)
-   **Access Key** -- This is the access key of the running Minio service
-   **Secret Key** -- This is the secret key of the running Minio service

The Advanced Configuration menu can be expended to provide more advanced options.
-   **Approval Enforced** - this toggle allows the Cloud Provider owner to control whehther approvals are needed for any request to create buckets using this provider. If enabled, then an approval request will show up under Notifications page for every provisioning request. If disabled, then provisioning requests are approved by default based on the entitlement and quota policies defined in the Cloud Provider.
-   **Quota Policies** -- these are pre-defined policies for setting quotas on the number of buckets. Multiple quota policies can be selected to customize controls per user or per group of users.

The optional fields allow you to enforce granular access controls and associate this provider with a quota policy.
-   **Entitled Users** -- these are the users who are allowed to use this Cloud Provider for object storage provisioning. The entitled users do not have permission to manage or delete this cloud provider and will not be able to view any of the credentials.

##   Next Steps

-   [**Create a Bucket**](https://github.com/hypergrid-inc/documentation/tree/master/object-storage)
