<figure>
<img src="http://www.hypergrid.com/wp-content/themes/hypergrid/img/logo.png" alt="" />
</figure>

Installing HyperForm On Premises On A Single Host 
===========================

### Step 1: Fill Out The Request Form
In order to get access to the install shell script, a user needs to fill out a form on http://dchq.co/hyperform-on-premise.html

### Step 2: Download The Installation Shell Script
Once the request form has been submitted, a URL to the software download page will be sent the users. This page contains the installation shell script along with some out-of-box application templates & plug-ins for Java, Ruby, Python, and PHP stacks.

Download the installation shell script (hyperform_server_install__version-number.sh) from the software download page.

### Step 3: Ensure That You Have A Supported Linux Host
HyperForm On-Premise has been extensively tested on Ubuntu -- but other Linux flavors including CentOS, Oracle Linux, Photon, Debian, CoreOS and Red Hat Enterprise Linux should work. It is recommended that you use Ubuntu for this installation. We support the versions that are certified with Docker – so please check Docker’s official page before attempting the HyperForm installation.

The installation requires at least 6 GB of Memory if you plan on running 1,000 containers or more. Our scalability tests were performed with up to 25,000 running containers with this configuration.

Of course, make sure that you have root access to the Linux host on which you’re going to install HyperForm On-Premise.

### Step 4: Run The Script On A Supported Linux Host
Again, make sure that you have root access to this Linux host, and then do the following.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sudo su
chmod +x hyperform_server_install__version-number.sh
./hyperform_server_install__version-number.sh
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

You will be prompted to set up the following:
-   (Required) Nginx SSL certificate
-   (Required) RabbitMQ CA certificate
-   (Recommended) Email Settings
-   (Optional) HTTP Proxy -- only if needed within your enterprise

The installation should not take more than 10 minutes – depending on your bandwidth and how fast the images can be pulled from Docker Hub.

### Step 5: Log Into HyperForm On-Premise And Save The RabbitMQ & Postgres Passwords For Your Record
Once the installation is complete, a confirmation message should show up with the following information.
-   Database Password
-   RabbitMQ Password
-   HyperForm On-Premise URL & Default Login Credentials

Make sure that you save this information for your records.

Log into HyperForm On-Premise using the default credentials (**admin@dchq.io** / **admin123**)

### Step 6 (IMPORTANT): Update The System Settings In The HyperForm Web Console
In order to ensure that new hosts registered can establish communication with RabbitMQ and that the agent can be installed correctly, please update the System Settings page.

Here are the entries that you need to update:
-   **dchq.agent.script.url** – https://www.dropbox.com/s/fvcfor3y2h6kez8/dchq_agent_install_v10.10_ssl.sh?dl=1
-   **dchq.win.agent.script.url** - https://www.dropbox.com/s/65tledwpws3eqhw/DCHQ_Agent_Install_Windows_v1.4_ssl.ps1?dl=1
-   **dchq.proxy.script.url** - https://www.dropbox.com/s/r6dph65s4ehjfvb/DCHQ_HyperVProxy_Install_Windows_v1.1.ps1?dl=1
-   **dchq.agent.connect.ip** – this is the public IP of the host that’s running HyperForm On-Premise
-   **dchq.agent.connect.port** – this is the host port that is mapped to RabbitMQ’s port 5671. By default, this is 5671.
-   **dchq.base.url**  – this is the URL for accessing HyperForm On-Premise. By default it is https://<DCHQ-IP>:443

### Step 7: Create A Cluster
You can check the full documentation for infrastructure provisioning here:
https://github.com/hypergrid-inc/documentation/clusters

Before we can register a Linux host, we need to create a cluster. This can be done by navigating to Clusters and then clicking on the + button. In the recorded videos, we made things simple and selected the default settings (i.e. Docker networking). 

### Step 8: Add An Existing Linux Host To Orchestrate Docker Application Deployments
Now that we’ve added our cluster, we will register an existing Linux host by navigating to **Virtual Machines** and then clicking on the + button to select **Linux Host/VM**.

Here are the parameters required:
-   Name: This could be any string value (e.g. DEV Server)
-   IP: This is the IP of the host you’re trying to register
-   Cluster: Select the cluster that you’ll be associating this server with

**IMPORTANT** – once you click **Save**, an auto-generated script will be provided that needs to be executed on the Linux host you’re trying to add.

The script expects at least 3 arguments and would like something like this:

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
curl -Ls  <dchq.agent.script.url> | bash -s <DCHQ Server Key> <dchq.agent.connect.ip> <dchq.agent.connect.port>
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

All of these parameters can be overridden in the **System Settings** page by the Cloud Admin.

### Step 9: Deploy One Of The Out-Of-Box Application Templates
You can check the full documentation on application modeling and deployment here:
https://github.com/hypergrid-inc/documentation/blueprints/docker-compose-v1

Navigate to the **Library* and then click **View** on any of the available application templates.

Select the cluster and then click on **Run**.
