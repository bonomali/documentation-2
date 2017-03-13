<figure>
<img src="http://www.hypergrid.com/wp-content/themes/hypergrid/img/logo.png" alt="" />
</figure>

OVH Public Cloud - Cloud Provider Registration
===========================

##   Pre-requisite Steps

Before registering a Cloud Provider for OVH, a user need to complete the following steps on OVH.

**Add a User for OpenStack**

1. Log in the OVH management console:
https://ca.ovh.com/manager/login/

2. Click on Public Cloud and create a new Project (if not already created)

3. Click on Project Management and Consolidation.

4. Click on OpenStack.

5. Click on Add User to generate a new token.

6. Save the ID and Password.

7. Click on the configuration icon and select "Downloading an OpenStack configuration file". IMPORTANT -- make sure you're completing this task in the region in which you plan on launching instances.

Open that file and copy the OS_TENANT_NAME. This will be needed along with the ID and Password when registering the Cloud Provider.

**Create a Private Key for the OpenStack Project**

Navigate to the Access and Security page and log in using the ID and Password created earlier for OpenStack.
https://horizon.cloud.ovh.net/project/access_and_security/

-   Click on the "Key Pairs" tab. Make sure that the region selected in the top matches the region on which you plan on launching instances.
-   Click on Create Key Pair and save the generated PEM file.


##   Register a Cloud Provider for OpenStack

You can now register a Cloud Provider for OVH Public Cloud by navigating to **Cloud Providers** and then clicking on the **+New** button to select **OpenStack**. The required fields are:
-   **Endpoint URL**: https://auth.cloud.ovh.net/v2.0
-   **Username**: OS_TENANT_NAME:ID (e.g. 6756121681216381:p4yVY12A6tXN). The OS_TENANT_NAME can be retrieved from the OpenStack config file (openrc.sh). The ID is from the User created for OpenStack.
-   **Password**: This is the password for the User created for OpenStack.


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
