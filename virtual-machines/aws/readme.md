<figure>
<img src="http://www.hypergrid.com/wp-content/themes/hypergrid/img/logo.png" alt="" />
</figure>

Provisioning Virtual Machines on AWS
===========================

A user can provision AWS EC2 instances through a UI-based workflow or by defining a simple YAML-based Machine Blueprint that can be requested from the Self-Service Library.  

Before completing the provisioning request, here are the critical steps that need to be completed first.
-   Retrieve the **AMI ID** in the Region of your choosing via the AWS EC2 Management Console.
-   A user can securely store the private key in the **Credentials Store**. This can be done by navigating to **Cloud Providers** and then clicking on the **+New** button to select **Credentials**. The username (e.g. ubuntu) and the private key (i.e. PEM file content) need to be provided. Once this credential item is saved, then click **Edit** on the new item saved to copy the newly **generated ID** for this credential item.

**UI-based Workflow** – A user can request an AWS EC2 instance by navigating to **Machines** and then clicking on the **+New** button to select **Amazon EC2**. Once the Cloud Provider is selected, a user can select the following options:
-   **Name Prefix** – the VM prefix that will be used for the new VM
-   **Region** -- select the AWS Region. *Important* - please do not select the zones within a region. For example, us-west-1 is support but not us-west-1a
-   **AMI** -- copy and paste the AMI ID from the AWS EC2 Management Console followed by the region (e.g. us-west-1/ami-d8bdebb8)
-   **Instance Type** -- select the instance type (e.g. t2.medium)
-   **Security Group** -- select an already created Security Group. Make sure that the appropriate inbound ports are open for expected application deployments. If no security group is selected, then a new one is created with inbound port 22 opened for SSH connection.
-   **Key Pair** -- select the key pair that was created earlier. Important - if you would like to select an existing key pair, make sure that the PEM file is stored in the Credential Store first as per the previous steps above.

A user can expand the **Advanced Configuration** to configure additional options.
-   **Subnet ID** -- select the subnet that should be used for the newly provisioned AWS instance. If no subnet is selected, then the default one in the Availability Zone will be used.
-   **IAM Role** -- specify an already created IAM Role from AWS IAM Management Console
-   **Number of Instances** - allowing users to specify the number of VMs to be provisioned

Finally, a user can specify other options.
-   **Skip Agent Install** -- this option can be selected if the VM template has the HyperCloud agent already pre-installed
-   **Username** -- enter the username that will be used to SSH into the machine (e.g. ubuntu). By default, the root user will be used for Linux machines.
-   **Password** --  select the stored Private Key that is stored in the Credentials Store. The format of this entry is {{credentials | 2c91808759209070015921ef16ac3d5a}}. The credentials ID can be retrieved by navigating to
-   **Cluster** -- this is the HyperCloud cluster that is created by the user

A user can then click on the **Machine Compose** button to generate a YAML-based Machine Compose template. This can be used to create your own standard Machine Compose template that can be shared with other users with granular access controls.

A user can create a Machine Compose template for **AWS EC2** by navigating to **Library** and then clicking on the **+Create New Blueprint** button to select **Machine Compose**.

The supported parameters for the Machine Compose template are summarized below:
-   **description**: Description of the blueprint/template
-   **instanceType**: Mandatory -- cloud provider specific value (e.g. t2.medium)
-   **region**: Mandatory -- the name of the region (e.g. us-west-1)
-   **image**: Mandatory - fully qualified image ID/name (e.g. us-west-1/ami-d8bdebb8)
-   **username**: This the username used to connect to the VM
-   **password**: This can reference a private key stored in the Credentials store. The ID of the credential item stored in the **Cloud Providers** > **Credentials** page will be needed. Here's the acceptable format: "{{credentials | 2c91802a520736224015209a6393098322}}"
-   **network**: Optional – Cloud provider specific value (e.g. default)
-   **subnet**: Optional – Cloud provider specific value (e.g. subnet ID for AWS)
-   **securityGroup**: Optional – Cloud provider specific value (e.g. default)
-   **openPorts**: Optional - comma separated port values
-   **aws_root_size**: Optional - the size of the disk to be attached to the instance in GB
-   **aws_root_encrypted**: Optional – a Boolean value for whether to encrypt the root disk or not
-   **aws_root_delete_on_termination**: Optional – a Boolean value for whether to delete the root disk on terminating the instance
-   **aws_device_name**: Optional – the path or directory for the device
aws_tags: key pair values that can be passed with the instance provisioning
-   **skipAgentInstall**: this is a Boolean value to indicate whether or not an agent should be installed as part of the VM provisioning workflow
-   **count**: Total no of VM's, defaults to 1.

Here's an example template:
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
AWS4GB:
  region: us-west-1
  description: AWS Ubuntu 14.04 t2.medium instance in us-west-1 region
  instanceType: t2.medium
  image: us-west-1/ami-d8bdebb8
  network: vpc-935ca2f6
  subnet: subnet-2fa2b569
  securityGroup: sg-b59131d0
  keyPair: awsdemo
  username: ubuntu
  password: "{{credentials | 2c91808659671a0701596b6e94fb109e}}"
  #aws_monitoring: true
  #aws_root_encrypted: false
  #aws_root_delete_on_termination: false
  #aws_device_name: /dev/sda1
  #aws_root_size: 10
  #aws_tags:
  #  billing_name: dchq
  #  created_by: DCHQ
  # plugins:
  #   - !plugin
  #     id: abcde
  count: 1
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

In addition to these supported parameters, you will also notice that this template is referencing a "plugin". A plugin can be invoked as follows:

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
  plugins:
    - !plugin
      id: <plugin-id>
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The plug-in can be created by Navigating to **Plugins** and then clicking on the **+New** button. A plug-in is a simple script that can run on either the server being provisioned or on the Docker container. The server plugins can be used for any number of configuration requirements:
-   Installing software using Puppet Modules, BASH, PowerShell, Perl, Python or Ruby scripts
-   Applying patches or udpdating configuration

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

Once the Machine Blueprint is saved, a user can request this machine from the Self-Service Library. A user can click View and then select the Cloud Provider and Cluster to use for provisioning the AWS EC2 Virtual Machines.
