<figure>
<img src="http://www.hypergrid.com/wp-content/themes/hypergrid/img/logo.png" alt="" />
</figure>

HyperCloud Block Storage Service 
===========================

HyperCloud's Block Storage Service (HBS) provides automated, self-service provisioning and mounting of high performance (SSD) block storage volumes for I/O intensive applications running on Linux or Windows, VMs or Containers. With a certified Docker Volume Plugin, deploying stateful applications on containers can be done in a single click while adhering to IT-defined entitlements, approvals, quotas, and quality of service (QoS) policies. 

The block storage devices provided by HyperCloud deliver low-latency and consistent I/O performance for running mission critical applications that require I/O intensive operations. With role-based access controls, entitlements, approval, quota and cost metering policies, IT administrators can manage block storage usage across the enterprise with cost visibility that promotes better control over spending.

HyperCloud also allows administrators to manage Quality of Service (QoS) controls to provide the required service levels to meet application-specific needs for storage performance. Once a block device is provisioned, users can scale storage up or down or provision and attach additional volumes to absorb unexpected spikes in traffic or growth in data storage size.  Lastly, HyperCloud allows users to create block storage volume blueprints as code controlled by user entitlements in order to simplify the management and version control of volume templates.

Here are the key benefits of HBS:
-   **High performance & fault tolerance.** High performance storage that provides fault tolerance to deliver high availability with fast performance across the data network.
-   **Policy-based Governance.** Leverage HyperCloud's governance framework to enable role-based access controls, entitlements, approval, quota and cost metering policies to manage block storage usage across the enterprise with the cost visibility needed to control spending.  
-   **Rapid block storage delivery.** Self-provisioning of block storage for system administrators means VMs and containers with dedicated, persistent storage volumes are delivered in minutes under the governance policies and security controls defined by IT
-   **QoS controls.** For the mission critical applications, QoS controls on HyperCloud’s all-flash storage were configured to prioritize I/O and provide the expected service levels 
-   **All-flash advantage.** Reducing costs by making maximum use of available storage space with all-flash’s smaller footprint.
-   **Inline erasure encoding.** Protecting the data before it leaves the host and eliminating the need for replicas.
-   **Linear scaling and pricing.** Adding capacity as needed with pay-as-you-go pricing.

Provisioning & Managing Volumes in HyperCloud
===========================

- [Provisioning Volumes](#provisioning-volumes)
- [Attach a Volume to a Running VM](#attach-a-volume-to-a-running-vm)
- [Detach a Volume from a Running VM](#detach-a-volume-from-a-running-vm)
- [Resize or Scale Up a Volume](#resize-or-scale-up-a-volume)
- [Clone a Volume](#clone-a-volume)
- [Timeline](#timeline)

Provisioning Volumes
----------

A user can provision volumes by navigating to the **Volumes** page, then clicking on the **+New** button to select **Create New**. Here are the required fields:

-   **Provider** -- this is the volume provider on which volumes will be provisioned
-   **Size** -- this is the size of the volume in GB (e.g. 2)

The Advanced Configuration allows users to configure more options:
-   **Name** -- this is the name of the new volume
-   **Type** -- a user can select either fixed or dynamic volumes
-   **Options** -- a user can pass more options based on the provider selected
-   **Entitled Users** -- these are the users who are allowed to use this volume

Attach a Volume to a Running VM
----------

A user can attach a volume to a running VM. This step will automatically mount and format the disk on the VM. To do this, a use can click the **Manage** dropdown and then select **Attach**. 

-   **Virtual Machine** -- this is the virtual machine on which a user can mount the un-attached volume

Detach a Volume from a Running VM
----------

A user can detach a volume from a running VM. This step will automatically unmount the disk from a VM. To do this, a use can click the **Manage** dropdown and then select **Detach**. 

Resize or Scale Up a Volume
----------

A user can resize or scale up a volume to address growing disk utilization. To do this, a use can click the **Manage** dropdown and then select **Resize**. 

-   **New Size** -- this is the new size of the volume in GB (e.g. 5)

Clone a Volume
----------

A user can clone a volume for backup or to make it available for testing. To do this, a use can click the **Manage** dropdown and then select **Clone**. 

-   **Clone Name** -- this is an automatically generated name of the new cloned volume but can be overridden by the user as long as the name is unique

Timeline
----------

A volume timeline tracks the history of all updates made to the volume along with the execution logs, the date of the update and the username of the user who made the change. With this audit trail, administrators can quickly troubleshoot issues and correlate incidents to changes made by users.



