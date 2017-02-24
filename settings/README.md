<figure>
<img src="http://www.hypergrid.com/wp-content/themes/hypergrid/img/logo.png" alt="" />
</figure>

System Settings 
===========================

The System Settings page allows the cloud administrators (super admins) to configure the IP of the platform as well as the paths to download the agent install scripts for the automated VM provisioning. The latest agent install scripts are uploaded on Dropbox on a frequent basis. However for on premises deployments, administrators can simply upload these scripts to a local file share that is accessible by HyperForm On Premises.

Here are the different settings that can be changed on this page.

| Parameter       | Description           |
| ------------- |:-------------:|
| dchq.agent.connect.ip     | This is the IP of the HyperForm platform | 
| dchq.agent.connect.port      | This is the port on which the agent communicates with RabbitMQ. By default it's 5671.     | 
| dchq.agent.script.url | This is the URL of the agent install script for Linux      | 
| dchq.base.url | This is the URL of the HyperForm platform. By default, it's https://hyperform-ip      | 
| dchq.title | This is the title that can be displayed instead of HyperForm for customer branding    | 
| dchq.win.agent.script.url | This is the URL of the agent install script for Windows      | 
