<figure>
<img src="http://www.hypergrid.com/wp-content/themes/hypergrid/img/logo.png" alt="" />
</figure>

HyperCloud Architecture 
===========================

HyperForm can automate the provisioning on either Hyper-V Nodes or Failover Clusters. To provision VM’s in a Hyper-V Cluster, the proxy agent needs to have read access to a shared file server on which the VHDX templates are saved. Additionally, a Cluster Shared Volume needs to be used to store the VM metadata (i.e. the VM destination).

The default inbound port needed for HyperForm to interact with the HyperCloud proxy is **443**. Managing VMs and applications is orchestrated via HyperForm's SSL-encrypted message queue service - provided by RabbitMQ. As a result, inbound port **5671** needs to be open to HyperForm on all VM's managed.


<figure>
<img src="https://dl.dropboxusercontent.com/u/416809645/Screenshots/HyperCloud%20Architecture.png" alt="" />
</figure>

