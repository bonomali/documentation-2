<figure>
<img src="http://www.hypergrid.com/wp-content/themes/hypergrid/img/logo.png" alt="" />
</figure>

Once an application is deployed, a user can access monitoring, alerts and notifications, continuous delivery using Jenkins, application backups, scale in/out, in-browser terminal to access the containers, log viewing, and container updates using custom plug-ins. 

**Table of Contents**  

- [Accessing the In-Browser Terminal for the Running Containers](#accessing-the-in-browser-terminal-for-the-running-containers)
- [Monitoring The CPU, Memory & I/O Utilization Of The Running Containers](#monitoring-the-cpu-memory--io-utilization-of-the-running-containers)
- [Replacing or Redeploying Containers When New Images Are Pushed into a Registry](#replacing-redeploying-containers-when-new-images-are-pushed-into-a-registry)
- [Scaling Out An Application](#scaling-out-an-application)
- [Executing Plug-Ins Post-Provision To Update An Application](#executing-plug-ins-post-provision-to-update-an-application)


Accessing the In-Browser Terminal for the Running Containers
----------

A command prompt icon should be available next to the containers’ names on the Apps page. This allows users to enter the container using a secure communication protocol through the agent message queue. A white list of commands can be defined by the Tenant Admin to ensure that users do not make any harmful changes on the running containers.

Monitoring The CPU, Memory & I/O Utilization Of The Running Containers
----------

Once the application is up and running, users can monitor the CPU, Memory, & I/O of the running containers to get alerts when these metrics exceed a pre-defined threshold. This is especially useful when performing functional & load testing.

A user can perform historical monitoring analysis and correlate issues to container updates or build deployments. This can be done by clicking on the Stats link. A custom date range can be selected to view CPU, Memory and I/O historically.


Replacing (Redeploying) Containers When New Images Are Pushed into a Registry
----------

For developers wishing to follow the “immutable” containers model by rebuilding Docker images containing the application code and spinning up new containers with every application update, HyperForm provides an automated container replacement workflow that pulls that latest image in a registry and replaces the running container with the latest image.
 
To set up a container redeployment (or replacement) profile, a user can select Container Redeploy Profile from the Action menu.

A user can then select one of the stored Docker registries and enter the name of the image that should be used when replacing the running container. To register a Docker Hub, Nexus, Artifactory or Quay account, a user should navigate to Cloud Providers and clicking on the + to select Docker Registries.


Scaling Out An Application
----------

If the running application becomes resource constrained, a user can scale out the application to meet the increasing load. Moreover, a user can schedule the scale out during business hours and the scale in during weekends for example.

To scale out the cluster of the .NET containers from 1 to 2, a user can click on the Actions menu of the running application and then select Scale Out. A user can then specify the new size for the cluster and then click on Run Now.
 
The service discovery plug-in configured for the load balancer (i.e. Nginx or Apache HTTP) will be automatically triggered to inject the container IP's of the new application servers into the default configuration file to facilitate the load balancing to the right services.

An application time-line is available to track every change made to the application for auditing and diagnostics. This can be accessed from the expandable menu at the bottom of the page of a running application.

Alerts and notifications are available for when containers or hosts are down or when the CPU & Memory Utilization of either hosts or containers exceed a defined threshold.


Executing Plug-Ins Post-Provision To Update An Application
----------

If a user would like to make simple changes to a deployed application then a custom script plug-in can be invoked to make such updates.
 
The Plug-ins framework, which relies on custom scripts that can be written in BASH, PowerShell, Perl, Ruby or Python, enables advanced application deployment and facilitates quick integration with any external service – including storage, networking or monitoring solutions.
 
To do this, a user must first create a plug-in by navigating to **Plug-ins**.
 
Then from the application’s page, a user can select **Plug-ins Run** from the **Actions** menu.

As user can then search for the plug-in and override the available arguments if needed (e.g. URL to fetch the latest .NET files). For ASP.NET Dynamic Compilation, a container restart may not be needed. However for other updates that require a quick restart of the container, then the Restart toggle can be selected.


