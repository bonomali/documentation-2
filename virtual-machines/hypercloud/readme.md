<figure>
<img src="http://www.hypergrid.com/wp-content/themes/hypergrid/img/logo.png" alt="" />
</figure>

Provisioning Virtual Machines on HyperCloud
===========================

A user can provision HyperGrid virtual machines on the newly created cluster either through a UI-based workflow or by defining a simple YAML-based Machine Blueprint that can be requested from the Self-Service Library.  

**UI-based Workflow** – A user can request a Hyper-V virtual machine by navigating to Machines and then clicking on the **+New** button to select **HyperCloud**. Once the Cloud Provider is selected, a user can select the following options:
-   **Name Prefix** – the VM prefix that will be used for the new VM
-   **Node** -- the HyperGrid (or Hyper-V) Node on which the new VM's will be provisioned
-   **Instance Type** -- pre-defined templates are available that specify the CPU, Memory, Disk and Generation for the VM (e.g. cpu=1,memory=2GB,disk=100GB,generation=1). A user can customize these value to his/her needs.
-   **Image** -- this is the .VHDX template that will be used for provisioning
-   **Network** -- this is the virtual network that will be used for the new VM
-   **Highly Available** – allowing users to provision the VM in HA-mode
-   **Skip Agent Install** -- this option can be selected if the VM template has the HyperForm agent already pre-installed
-   **Username** -- this is the username needed to log into the VM
-   **Password** -- this is the password needed to log into the VM
-   **Cluster** -- this is the HyperForm cluster that is created by the user
-   **VM Count** -- this is the number of VM's that can be provisioned simultaneously

A user can then click on the **Machine Compose** button to generate a YAML-based Machine Compose template. This can be used to create your own standard Machine Compose template that can be shared with other users with granular access controls.

A user can create a Machine Compose template for **HyperCloud** by navigating to **Library** and then clicking on the **+Create New Blueprint** button to select **Machine Compose**.

The supported parameters for the Machine Compose template are summarized below:
-   **description**: Description of the blueprint/template
-   **instanceType**: Mandatory -- cloud provider specific value (e.g. cpu=1,memory=4GB,disk=100GB,generation=1)
-   **region**: Mandatory -- the name of the Hyper-V Node
-   **image**: Mandatory - fully qualified path of the .VHDX template (e.g. \\VFCN10-AD\HyperForm\Template\HyperForm_Ubuntu-14.04_64_10.0.254.100.vhdx)
-   **username**: This the username used to connect to the VM
-   **password**: This can reference a private key stored in the Credentials store. The ID of the credential item stored in the Cloud Providers > Credentials page will be needed. Here's the acceptable format: "{{credentials | 2c91802a520736224015209a6393098322}}"
-   **network**: Cloud provider specific value (e.g. Virtual Switch1)
-   **affinity**: this is a Boolean value to enable High Availability option (e.g. true or false)
-   **skipAgentInstall**: this is a Boolean value to indicate whether or not an agent should be installed as part of the VM provisioning workflow
-   **count**: Total no of VM's, defaults to 1.

In addition to these supported parameters, you will also notice that this template is referencing a "plugin". A plugin can be invoked as follows:

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
  plugins:
    - !plugin
      id: <plugin-id>
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The plug-in can be created by Navigating to **Plugins** and then clicking on the **+New** button. A plug-in is a simple script that can run on either the server being provisioned or on the Docker container. The server plugins can be used for any number of configuration requirements:
-   Installing software using Puppet Modules, BASH, PowerShell. Perl, Python or Ruby scripts
-   Retrieving the CA certificate needed for the private Docker registry from a secure S3 bucket and then saving it in the right directory (e.g. /etc/docker/certs.d/<domain-name>:5000/ca.crt)

The Machine Compose template has additional advanced options.
-   **YAML** -- this is the actual machine blueprint allowing adminstrators to manage "infrastructure as code"
-   **Cloud Provider** -- the entitled cloud end-point associated with this machine blueprint
-   **Customizable Parameters** -- these are the parameters that can be exposed by the blueprint author allowing entitle blueprint consumers to override these parameters at provisioning (e.g. instance type or image)
-   **Cost Profiles** -- these are the cost profiles that you can create under Policies > Cost Profiles. You can define cost per resource on an hourly/weekly/monthly basis. You can attach multiple cost profiles to a single template -- e.g. different cost profiles for the instance type, EBS storage used, etc.
-   **Entitled Users** -- these are the users who are allowed to use this template to provision AWS instances. The entitled users do not have permission to manage or delete this template and will only be able to consume it.

Additionally, advanced configuration allow blueprint authors to manage blueprint visibility, license model and the image that best depicts this service in the self-service library.
-   **Image** -- this is the image that best depicts the service in the self-service library (e.g. Microsoft SQL Server or Red Hat Enterprise Linux)
-   **License Model** -- the two available options are "license included" and "bring your own license". With license included, it is expected from the blueprint provider (or owner) to include the license in the VM blueprint published. With bring your own license, the blueprint consumer would need to provide the valid license key post-provision.
-   **YAML Visibility** – the blueprint author can indicate whether or not users entitled to this blueprint should have read-only access or no visibility at all.

Granular entitlements and cost profiles allow IT administrators to control access to the blueprint and monitor cloud usage to control spending

Once the Machine Blueprint is saved, a user can request this machine from the Self-Service Library. A user can click View and then select the Cloud Provider and Cluster to use for provisioning the HyperGrid (Hyper-V) Virtual Machines.
