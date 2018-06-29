# Compute_Engine_GCP
- - - -
# Cloud Launcher
	* Google Cloud Launcher lets you quickly deploy functional software packages that run on Google Cloud Platform. Even if you are unfamiliar with services like Compute Engine or Cloud Storage, you can easily start up a familiar software package without having to manually configure the software, virtual machine instances, storage, or network settings.
	
	* Deploy a software package now, and scale that deployment later when your applications require additional capacity. Google Cloud Platform updates the images for these software packages to fix critical issues and vulnerabilities, but doesn’t update software that you have already deployed.

	* Most packages are free minus normal usage fees
	
- - - -
##### Choosing the correct GCP Compute service for your task
	* GCP has several options available for hosting your application on Google Cloud Platform. Each option can take advantage of the entire breadth of services offered by Cloud Platform, including storage, networking, big data products, and Google-grade security.
	* Bulk of this course will focus on GCP’s Compute options in Compute Engine, App Engine, and Container Engine 
	* Swiss army knife - choose the right tool for the job 
	* Your role as a Google Cloud Architect will be to choose the right tool based on the business and technical requirements you have to work with.
	* From an application deployment and development standpoint, all of the above options will get the job done and each have their pro/cons depending on your needs
	* There is no right or wrong answer, only which one is correct for your environment
	* Options roughly operate on a sliding scale flexibility on one end and managed abstraction on the other end
	* Guide: https://cloud.google.com/docs/choosing-a-compute-option
	* Blog decision guide: https://cloudplatform.googleblog.com/2017/07/choosing-the-rightcompute-option-in-GCP-a-decision-tree.html
- - - -
# Compute Engine
# What is Infrastructure as a Service?
	* One of three cloud computing models, the other two being Platform as a Service (PaaS) and Software as a Service (SaaS)
	* It is a form of cloud computing that provides virtualized computing resources over the Internet
	* Often referred to as the core layer of cloud computing. Behind the scenes, PaaS and SaaS are running on an IaaS layer.
	* Deals with Virtual Machines and (in some cases) virtual networks
	* What is considered to be ‘infrastructure’ in this case? What goes into a virtual machine?
		* Best definition is a virtual version of a physical PC/server. Just as a physical computer has a CPU, memory, hard drive, an operating system, and firewall to manage network traffic, so does a virtual machine.
		* Like a physical machine, it is up to the customer to manage the above aspects, as well as perform typical OS maintenance such as updates.
		* 
# Google Compute Engine Overview
#### What is Google Compute Engine?
	* Google Compute Engine delivers virtual machines running in Google’s innovative data centers and worldwide fiber network. Compute Engine’s tooling and workflow support enable scaling from single instances to global, load-balanced cloud computing.

#### What makes Google Compute Engine unique?
	* Industry Leading Price & Performance
		* Compute Engine VMs boot quickly and are consistently high performance.
		* Offers local solid state drive (SSD) performance.
		* Positioned as the higher performance option
			* ”Google Compute Engine ranked #1 in price-performance”(https://lp.google-mkto.com/rs/248-TPC-286/images/Cloud-Spectator-Best-Hyperscale-Cloud-Providers.pdf)

	* Low Cost, Automatic Discounts
		* Google bills in minute-level increments (with a 10-minute minimum charge), so you only pay for the compute time you use. With sustained use discounts, they automatically give you discounted prices for long-running workloads with no upfront commitment required.
	* High speed, secure, private network
		* Global private fiber network
		* Connections between data centers on private high speed connections
		* Same network infrastructure used by Google
	* Extremely Flexible
		* Create custom images
		* Low cost Pre-emptible VM’s for batch workloads
		* Custom machine types (CPU/memory specs)
		* Resize disks with no downtime
		* Create metadata and startup scripts

# Snapshots and Images
Similarities:
	* Can be used to create a new instance within the same project and in different zones.
Differences:
	* Intended purpose:
	* Snapshots are different from images, which are used create instances and instance templates. Snapshots are useful for periodic backup of the data on your persistent disks. You can create snapshots from persistent disks even while they are attached to running instances.
	* i.e. backup and disaster recovery
	* Lower cost than custom images
	* Differential backups – only the data changed since the last snapshot is recreated
# Pre-emptible VM’s and groups
**What are Preemptible VM’s?**
		* Short lived, low cost VM
		* Costs less than a typical instance (up to 80% cheaper)
		* Short lifespan, max of 24 hours
		* Excellent for short term batch processing
		* Compute-intensive workloads
		* Deploy in large numbers as needed
		* Fault tolerant workloads
**What are Instance Groups?**
		* Create and manage groups of virtual machine (VM) instances so that you don’t have to individually control each instance in your project.
		* Managed and Unmanaged
		* Managed groups:
		* Automatically scale up and down as needed
		* Work with load balancing – distributing traffic among instances
		* If an instance crashes, it is auto-recreated
		* Instance templates define and deploy the group
		* Think of it as a ‘hive mind’ effect. Many machines acting as one.
#cloud/gcloud/architect_exam