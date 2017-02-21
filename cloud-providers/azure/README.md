<figure>
<img src="http://www.hypergrid.com/wp-content/themes/hypergrid/img/logo.png" alt="" />
</figure>

Microsoft Azure Resource Manager - Cloud Provider Registration
===========================

##   Pre-requisite Steps

Before creating a Cloud Provider, you will need to create an Application in the Active Directory and capture the required information as per the steps below. You will also need to create a Resource Group, a Storage Account, a Virtual Network and an Availability Set.

Here are the detailed steps.
1.   Go to Azure Active Directory on the Azure Portal. Click on App Registrations and click on Add to add a new application.
2.   Copy the Application ID. This will be mapped to **Application Client ID** when registering a Cloud Provider for Microsoft Azure Resource Manager in HyperForm.
3.   Copy the Directory ID by navigating to Properties. This will be mapped to **Tenant ID** when registering a Cloud Provider for Microsoft Azure Resource Manager in HyperForm.
4.   Click on Keys and then enter the name of the key along with the expiration date. Click on Save to generate a new key for this application. Important - copy the key's value after you click save. This will be the **"Application Client Secret"** when creating a Cloud Provider for Microsoft Azure Resource Manager in HyperForm.
5.   Add the appropriate Owners to this application by clicking on Owners and then clicking on Add.
6.   Copy the **Subscription ID** by navigating to Subscriptions and then selecting the one you would like to use. Add the new Application to the Subscription by navigating to Access Control (IAM) and then clicking on Add. Select the role as the Owner and then search for the application that was added earlier.
7.   Create a Resource Group and add the Application user as “Owner” if not already added.
8.   (Optional) Create a Storage Account and add it to the newly created Resource Group.
9.   (Optional) Create a Virtual Network and add it to the newly create Resource Group
10.   (Optional) Create an Availability Set and assign it to the Resource Group
11.   (Optional) Create a Network Security Group and assign it to the Resource Group. Important - make sure that the SSH port 22 is open for to the HyperForm platform. You can also open any other ports needed for your applications (e.g. 80, 8080, etc.).

##   Register a Cloud Provider for Microsoft Azure Resource Manager

You can now register a Cloud Provider for Microsoft Azure by navigating to **Cloud Providers** and then clicking on the **+New** button to select **Microsoft Azure (RM)**. The required fields are:
-   Application Client ID: *This is the **Application ID** from above*
-   Application Client Secret: *This is **Key** value from above*
-   Subscription ID: *This is obtained from the **Subscription** for which the application is assigned as an Owner*
-   Tenant ID: *This is the **Directory ID** from above*

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

