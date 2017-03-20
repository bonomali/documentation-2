<figure>
<img src="http://www.hypergrid.com/wp-content/themes/hypergrid/img/logo.png" alt="" />
</figure>

**Table of Contents**  

- [Registering already running servers or VMs](#registering-already-running-servers-or-vms)
- [Provisioning VMs on HyperCloud or other supported clouds](#provisioning-vms-on-hypercloud-or-other-supported-clouds)
- [Managing VMs post-provision](#managing-vms-post-provision)

Registering already running servers or VMs
----------

A user can register already running servers or VMs. Both Linux and Windows are supported. Bringing already provisioned machines under management in HyperCloud allows administrators to monitor CPU, Memory and Disk Utilization, get alerts when performance metrics exceed a pre-defined threshold, access an in-browser terminal for quick troubleshooting, and apply controlled updates using IT-approved scripts (e.g. BASH, PowerShell, Puppet, etc.) to standardize application updates and configuration changes.

To register a running machine, a user needs to provide the IP address and then run an automatically generated script to install the HyperCloud agent.
-   Register an existing [**Linux machine**](https://github.com/hypergrid-inc/documentation/tree/master/virtual-machines/register-linux-machine)
-   Register an existing [**Windows machine**](https://github.com/hypergrid-inc/documentation/tree/master/virtual-machines/register-windows-machine)


Provisioning VMs on HyperCloud or other supported clouds
----------

A user can provision virtual machines on HyperCloud or any of the other 15 other clouds and virtualization platforms supported – like VMware vSphere, OpenStack, Microsoft Hyper-V, Amazon Web Services, Microsoft Azure and others.

This can be done by clicking on the **+New** button to select your cloud of choice.
-   [HyperCloud](https://github.com/hypergrid-inc/documentation/tree/master/virtual-machines/hypercloud)



Managing VMs Post-Provision 
===========================

HyperCloud automates both the provisioning and the lifecycle management operations for both infrastructure and application services – allowing teams to access monitoring, alerts, in-browser terminals, logs, audit trails, VM timeline, and controlled updates using IT-approved scripts. By adopting automated lifecycle management, IT could automate downstream operations, lowering the cost to apply patches, scale out resources, and update configurations.

- [In-Browser Terminal](#in-browser-terminal)
- [Monitoring](#monitoring)
- [Plugins](#plugins)
- [Timeline](#timeline)

In-Browser Terminal
----------

An in-browser terminal to the provisioned machine (for both Linux and Windows) is also accessible. This can be accessed by navigating to **Machines** and then selecting **Terminal** icon. This provides administrators with quick access to the virtual machine for troubleshooting

Monitoring
----------

Once a VM is provisioned, a user can monitor key statistics like CPU, Memory, Disk Utilization and Containers Running. This can be done by navigating to **Virtual Machines** and then selecting **Monitoring** or Stats from the **Manage** drop-down menu. The historical monitoring view allows IT administrators to quickly identify issues and troubleshoot performance problems.

Plugins
----------

Controlled updates can be be applied using IT-approved scripts (e.g. BASH, PowerShell, Puppet, etc.) to standardize application updates and configuration changes

The Plug-ins framework, which relies on custom scripts that can be written in BASH, PowerShell, Puppet, Perl, Ruby or Python, enables controlled updates to VM’s as well as containers.  These plug-ins can be invoked at more than 15 different lifecycle stages to enable service discovery, on-the-fly containerization and application storage automation.

To apply an update to the machine (e.g. a configuration or software change), a user can navigate to **Machines** and then selecting **Plugins (Run)** from the **Manage** drop-down menu. A user can then search for a plug-in he/she is entitled to use and click on Run Now to execute the plug-in..

Timeline
----------

A VM timeline tracks the history of all updates made to the VM along with the execution logs, the date of the update and the username of the user who made the change. With this audit trail, administrators can quickly troubleshoot issues and correlate incidents to changes made by users.
