<figure>
<img src="http://www.hypergrid.com/wp-content/themes/hypergrid/img/logo.png" alt="" />
</figure>

Registering Windows Machines in HyperCloud
===========================

A user can register an already running virtual machine. This can be done by navigating to **Virtual Machines** and then clicking on the **+New** button. A user can then select the **Windows Host/VM** workflow and complete the required fields.
-   **Name** -- the name of the server you would like to register. This does not necessarily need to be the actual hostname.
-   **IP Address** -- this is the IP address of the server you're registering.
-   **Cluster** -- this the cluster that the new server will be part of. Make sure that you create the [**cluster**](https://github.com/hypergrid-inc/documentation/tree/master/clusters) first -- before registering servers or provisioning new ones.

Once a user clicks **Save**, then an automatically generated script appears. You can run this script on the host you're trying to register as an Administrator for Windows machines. Based on the cluster selected, the generated script would include the correct network configuration. 
-   **docker.skip** – for VM’s provisioned into a non-Docker cluster
-   **docker.local** – for VM’s provisioned into a Docker cluster
-   **weave.node** – for VM’s provisioned into a Weave cluster

The location of the agent install script can be changed by navigating to **Identity** > **System Settings**.

This task can be automated programmatically using our REST API’s for creating [Docker Servers](https://dchq.readme.io/docs/dockerservers)
