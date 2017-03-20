<figure>
<img src="http://www.hypergrid.com/wp-content/themes/hypergrid/img/logo.png" alt="" />
</figure>

HyperCloud Portal Documentation 
===========================

HyperCloud Portal (previously HyperForm) is the management console of HyperCloud, providing integrated compute, storage, networking, application and container services in a full-stack offering that is delivered on premises and on a pay-as-you-go consumption model.

HyperCloud combines the agility, simplicity and economics of public cloud services with the customization, control and security of on-premises solutions. 

The self-service library in HyperCloud enables self-provisioning of infrastructure, storage, network, database, and application services in minutes, not days! Even more essential for companies in highly regulated industries, all provisioning workflows initiated through the self-service library adhere to IT-defined governance controls, entitlements, approvals and quota policies – allowing IT to be in full control while providing agility and flexibility to application development teams.

This documentation library contains all the instructions for registering cloud providers, provisioning virtual machines, creating and mounting block storage volumes, managing object storage, and deploying applications on containers, VMs or bare-metal servers.

**Getting Started with HyperCloud**  

- [HyperCloud Compute Service](#hypercloud-compute-service)
- [HyperCloud Block Storage Service](#hypercloud-block-storage-service)
- [HyperCloud Object Storage Service](#hypercloud-object-storage-service)
- [HyperCloud Application Service](#hypercloud-application-service)
- [HyperCloud Container Service on Docker Swarm](#hypercloud-container-service-on-docker-swarm)
- [HyperCloud Cloud Management Service](#hypercloud-cloud-management-service)

HyperCloud Compute Service
----------

<figure>
<img src="https://dl.dropboxusercontent.com/u/416809645/Screenshots/compute-service.png" alt="" />
</figure>

Accelerate the deployment of mission-critical applications with flexible compute services

-   On-Demand, Self-Service VM Provisioning
-   Performance & Cost Monitoring
-   VM Operations & Lifecycle Management

**Get started with the compute service**

-   Register a [**Cloud Provider**](https://github.com/hypergrid-inc/documentation/tree/master/cloud-providers/hypercloud) for HyperCloud
-   Create a [**Compute Cluster**](https://github.com/hypergrid-inc/documentation/tree/master/clusters)
-   Provision VMs or register already running servers from the [**Virtual Machines**](https://github.com/hypergrid-inc/documentation/tree/master/virtual-machines) page. Generate **machine blueprints** that can be requested from the self-service library to standardize VM provisioning in your organization while adhering to IT-defined governance controls, entitlements, approvals and quota policies.


HyperCloud Block Storage Service
----------

<figure>
<img src="https://dl.dropboxusercontent.com/u/416809645/Screenshots/block-storage-service.png" alt="" />
</figure>

Power the most I/O intensive applications with high performance, fault-tolerant block storage devices
-   Certified Docker Volume Plugin
-   High Performance & Fault Tolerance
-   QoS Controls for Mission Critical Apps


**Get started with the block storage service**

-   Register a [**Volume Provider**](https://github.com/hypergrid-inc/documentation/tree/master/cloud-providers/hypercloud) for HyperCloud
-   Provision a [**Volume**](https://github.com/hypergrid-inc/documentation/tree/master/volumes) and then **attach** the volume to a running VM. **Resize** or scale up a volume to accommodate for the growing disk utilization and **clone** a volume to create backups of your mission-critical data.


HyperCloud Object Storage Service
----------

<figure>
<img src="https://dl.dropboxusercontent.com/u/416809645/Screenshots/object-storage-service.png" alt="" />
</figure>

Enable backups, big data analytics and static website hosting with highly durable, scalable, and secure object storage
-   Amazon S3 Compatible
-   Durable, Scalable and Available
-   Policy-based Governance

**Get started with the object storage service**

-   Provision a [**virtual machine**](https://github.com/hypergrid-inc/documentation/tree/master/virtual-machines) and then create and attach two [**volumes**](https://github.com/hypergrid-inc/documentation/tree/master/volumes) to the VM with the expected size for the object storage
-   Provision the Minio blueprint from the **Library** page to roll out object storage service to your users. Map the volumes in the blueprint to the ones created in the previous step. Customize the access key and secret key or generate random keys using {{alphanumeric | 12}} as a value to the environment varaiables 


HyperCloud Application Service
----------

<figure>
<img src="https://dl.dropboxusercontent.com/u/416809645/Screenshots/application-service.png" alt="" />
</figure>

Create, automate, deploy, and manage your applications in the cloud
-   Advanced Multi-VM & Container Orchestration
-   Automated Network Isolation & Segmentation
-   Any App, Any Scale

**Get started with the application service**

-   TBD


HyperCloud Container Service on Docker Swarm
----------

<figure>
<img src="https://dl.dropboxusercontent.com/u/416809645/Screenshots/container-service.png" alt="" />
</figure>

Rapidly and reliably build and deliver applications using containers on automatically provisioned Docker Swarm Clusters
-   Supports Linux & Windows Containers
-   Lift, Containerize & Shift Existing Apps
-   Service Discovery, Monitoring, Updates & Scaling


**Get started with the container service**

-   Create a [**Docker Swarm Cluster**](https://github.com/hypergrid-inc/documentation/tree/master/clusters)
-   Provision VMs or register already running servers from the [**Virtual Machines**](https://github.com/hypergrid-inc/documentation/tree/master/virtual-machines) page. 
-   (Optional) Regiser your **Docker Registry** and build your [**Docker images**](https://github.com/hypergrid-inc/documentation/tree/master/container-images)
-   Create and then deploy your [**Docker Compose**](https://github.com/hypergrid-inc/documentation/tree/master/library/docker-compose-v1) blueprint from the **Library** page


HyperCloud Cloud Management Service
----------

<figure>
<img src="https://dl.dropboxusercontent.com/u/416809645/Screenshots/cloud-mgmt-service.png" alt="" />
</figure>

A centralized console enables you to manage resources, workloads, and operations across any cloud, ensuring secure use of public clouds.
-   Automates Self-Service Provisioning of VMs & Apps on 15+ Clouds – vSphere, Hyper-V, OpenStack, Azure, AWS, etc.


**Get started with the cloud management service**

-   Register a [**Cloud Provider**](https://github.com/hypergrid-inc/documentation/tree/master/cloud-providers/) for any of the 18 clouds and virtualization platforms supported - including VMware vSphere, Microsoft Hyper-V, OpenStack, Microsoft Azure, AWS and others.
-   Create a [**Compute Cluster**](https://github.com/hypergrid-inc/documentation/tree/master/clusters) or a [**Container Cluster**](https://github.com/hypergrid-inc/documentation/tree/master/clusters)
-   Provision VMs or register already running servers from the [**Virtual Machines**](https://github.com/hypergrid-inc/documentation/tree/master/virtual-machines) page. Generate **machine blueprints** that can be requested from the self-service library to standardize VM provisioning in your organization while adhering to IT-defined governance controls, entitlements, approvals and quota policies.




