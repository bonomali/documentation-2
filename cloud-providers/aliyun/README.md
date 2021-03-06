<figure>
<img src="http://www.hypergrid.com/wp-content/themes/hypergrid/img/logo.png" alt="" />
</figure>

Alibab Aliyun - Cloud Provider Registration
===========================

##   Pre-requisite Steps

Before creating a Cloud Provider, you will need to obtain the Access Key and the Secret Key from the **"AccessKeys"** section in the Aliyun Console.


##   Register a Cloud Provider for Aliyun

You can now register a Cloud Provider for Aliyun by navigating to **Cloud Providers** and then clicking on the **+New** button to select **Aliyun (Alibaba)**. The required fields are:
-   Access Key ID: *This is the **Access Key** from Aliyun*
-   Secret Key ID: *This is **Secret Key** value from Aliyun*

The Advanced Configuration menu can be expended to provide more advanced options.
-   **Group** - this is the default VM prefix for VM's provisioned using this Cloud Provider. A user can override this value when provisioning VM's via the UI-based workflow or when creating Machine Blueprints.
-   **Free Form Provision** - this toggle allows the Cloud Provider owner to control whehther users can provision VM's via a UI-based workflow. If enabled, then users can provision VM's from the UI-based workflows under the Machines page. If disabled, then users will need to provision VM's via published Machine Blueprints in the Library.
-   **Trusted Blueprints** -- these are the Machine Compose templates that can be used with this cloud provider. For example, if a Tenant Admin wishes to restrict users to provisioning 4GB machines on certified operating systems, then users will not be able to use this cloud provider to provision any other machine.
-   **Approval Enforced** - this toggle allows the Cloud Provider owner to control whehther approvals are needed for any provisioning request using this provider. If enabled, then an approval request will show up under Notifications page for every provisioning request. If disabled, then provisioning requests are approved by default based on the entitlement and quota policies defined in the Cloud Provider.
-   **VM Limit** -- this is the maximum number of virtual machines that can be used with this cloud provider
-   **Quota Policies** -- these are pre-defined policies for setting quotas on the number of VM's or the cost of VM's. Multiple quota policies can be selected to customize controls per user or per group of users.
-   **Lease** - this is the lease (or the maximum amount of time) for provisioned VM's. If a lease expires, then the provisioned VM will be automatically destroyed. Users can request a lease extension from the Machines page.

The optional fields allow you to enforce granular access controls and associate this provider with a quota policy.
-   **Entitled Users** -- these are the users who are allowed to use this Cloud Provider for infrastructure provisioning. The entitled users do not have permission to manage or delete this cloud provider and will not be able to view any of the credentials.

Once saved, a user can test the connection by clicking on **Test Connection** button.

##   Next Steps

-   Create a Cluster: https://github.com/hypergrid-inc/documentation/edit/master/clusters
-   Provision a VM: https://github.com/hypergrid-inc/documentation/edit/master/virtual-machines
