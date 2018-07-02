# GCP - Compute 
- - - -
**Compute Engine VM**

High-Performance, Scalable VMs

Google Compute Engine delivers virtual machines running in Google's innovative data centers and worldwide fiber network. Compute Engine's tooling and workflow support enable scaling from single instances to global, load-balanced cloud computing.
![](GCP%20-%20Compute/0D915D63-96D3-4F0E-9C03-12983D549463.png)

Compute Engine’s VMs boot quickly, come with persistent disk storage, and deliver consistent performance. Google’s virtual servers are available in many configurations including predefined sizes or the option to create Custom Machine Types optimized for your specific needs. Flexible pricing and automatic sustained use discounts make Compute Engine the leader in price/performance.
![](GCP%20-%20Compute/976217AD-52A6-4E47-90FE-E7AEA8E87FD5.png)

Low Cost, Automatic Discounts

Google bills in second-level increments, so you only pay for the compute time you use. With sustained use discounts, Google automatically gives you discounted prices for long-running workloads with no up-front commitment required.


Fast & Efficient Networking

Create large compute clusters that benefit from strong and consistent cross-machine bandwidth. Connect to machines in other data centers and to other Google services using Google's private global fiber network. Create an instance, check the network configs, run some tests.


Environmentally Friendly Global Network

Google’s infrastructure is entirely carbon-neutral. Google’s global network of data centers consume 50% less energy than the typical datacenter and we purchase enough renewable energy to match 100% of the energy consumed by our global operations. Google is growing its global datacenter footprint so your applications can run closer to your customers and distribute geographically for resiliency.

 Resize your clusters, create machine images, virtualize your network, use Preemptible VMs for batch workloads and create Custom Machine Types to optimize for your specific needs. Our pricing model won't lock you into obsolete machine types with upfront agreements.
```yaml
    // CREATE INSTANCE WITH 4 vCPUs and 5 GB MEMORY
    gcloud compute instances create my-vm --custom-cpu 4 --custom-memory 5

    // ENABLE PREEMPTIBLE OPTION
    gcloud compute instances create my-vm --zone us-central1-b --preemptible
```
- - - -
# Compute Engine Features
Scalable, High-Performance Virtual Machines

##### Predefined Machine Types
Compute Engine offers predefined virtual machine configurations for every need from micro instances to instances with up to 160 vCPUs and 3.75 TB of system memory. 

##### Custom Machine Types
Create virtual machines with the shape (i.e. vCPU and memory) that is right for your workloads. By tailoring a Custom Machine Type to your specific needs you can realize significant savings. 

##### Persistent Disks
Network storage, up to 64 TB in size, can be attached to VMs as persistent disks. You can create persistent disks in HDD or SSD formats. If a VM instance is terminated, its persistent disk retains data and can be attached to another instance. You can also take snapshots of your persistent disk and create new persistent disks from that snapshot. 

##### Local SSD
Compute Engine offers always-encrypted local solid-state drive (SSD) block storage. Unlike standard persistent disks, local SSDs are physically attached to the server hosting the virtual machine instance offering very high input/output operations per second (IOPS) and very low latency compared to persistent disks. Local SSD sizes up to 3 TB are available for any VM with at least 1 vCPU. 

##### Transparent Maintenance
    Our innovative datacenters and Live Migration technology enable proactive infrastructure maintenance, improving reliability and security. Your live VMs are automatically moved to nearby hosts, even if your VMs are under extreme load, while underlying host machines undergo maintenance. You won't have to reboot your VMs due to host software updates or even some classes of detectable hardware failure. 

##### Global Load Balancing
Global load-balancing technology helps you distribute incoming requests across pools of instances across multiple regions, so you can achieve maximum performance, throughput and availability at low cost. 


##### Linux & Windows Support
Run your choice of OS, including Debian, CentOS, CoreOS, SUSE, Ubuntu, Red Hat, FreeBSD, or Windows Server 2008 R2, 2012 R2, and 2016. You can also use a shared image from the Cloud Platform community, or bring your own. 

##### Batch Processing
Cost effectively run large compute and batch jobs using Preemptible VMs. Fixed pricing and no contracts or reservations make it easy: simply check a box when you create the VM and turn them off when the work is done. 

##### Compliance & Security
All data written to persistent disk in Compute Engine is encrypted on the fly and then transmitted and stored in encrypted form. Google Compute Engine has completed ISO 27001, SSAE-16, SOC 1, SOC 2, and SOC 3 certifications, demonstrating our commitment to information security. 

##### Per-Second Billing
Google bills in second-level increments. You pay only for the compute time that you use. 

##### Automatic Discounts
With Sustained Use Discounts, we automatically give you discounted prices for long-running workloads with no sign-up fees or up-front commitment. 

##### Commitment savings
With Committed Use Discounts you can save up to 57% with no upfront costs or instance-type lockin. 

##### Containers
Run, manage and orchestrate Docker containers on Compute Engine VMs with Google Kubernetes Engine. 
- - - -
#cloud/gcloud/engineer_cert/GCP-DeepDive
