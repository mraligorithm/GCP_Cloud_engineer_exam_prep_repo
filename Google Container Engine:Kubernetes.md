# Google Container Engine/Kubernetes
### What are Containers?
	* Method of operating system virtualization that lets you run an application plus dependencies in isolated processed called containers

	* Simply defined: a container contains the entire runtime environment, including application code, configurations, and dependencies, libraries and other binaries - and packages them into self-contained building blocks 
			* Differences in host OS’s and underlying infrastructure are abstracted away
	
	* With containers, it is easy to get software to run reliably across different computing environments 
			* Developer’s laptop to test environment, to staging environment, and to production 
			* From physical PC to a VM in private or public cloud 
			* Before containers, different software environments can break programs
	* Docker is one of the more popular container technologies
	* How are containers different from standard VMs (IaaS)?
			* A VM contains an entire operating system packaged with the application
			* A container only runs OS kernel. It is much more lightweight and uses less resources
	* Other benefits include:
			* Faster start time since no host OS to boot
			* Smaller size
			* Broken down into easier to manage modules
				* Updating application only required updating the needed module
			* Docker - popular container technology, and the type Container Engine uses
				* For this lesson, the term “docker” and container are synonymous
Imagine containers as containers on a large cargo ship. Each container can be added and removed, stacked, etc as a self contained entity. Same concept with software containers.

- - - -
# What is Kubernetes?
Kubernetes is an open-source system for automating deployment, scaling, and management of containerized applications.

**With Kubernetes, you can:**
	* Deploy your applications quickly and predictably.
	* Scale your applications on the fly
	* Roll out new features seamlessly with no downtime
	* Limit hardware usage to required resources only.

# What is Google Container Engine (GKE)?
	* It is a managed environment for deploying containerized applications 
			* Uses Compute Engine instances and resources
	* Falls between Compute Engine and App Engine for managed services vs. granular control
	* Google has been running containers in their internal production workloads for over 15 years 
	* As a managed service, many details are handled for you:
			* Simply set CPU, memory, and storage requirements, and Container Engine will provision and manage resources automatically
	* Self-healing - replication strategies, monitoring, and automated repairs result in high reliability and availability
	* Autoscaling - GKE automatically scales up and down based on load to meet demand
	* Runs Kubernetes - an open source container orchestrator that Google invented
			* No vendor lock in - take workloads out of GKE and run anywhere Kubernetes is supported, including your own on-premise services
	* Runs a custom OS, called Container-Optimized OS
			* Comes with Docker container runtime and all Kubernetes components needed for easy deployment
			* Automatically updated, no server management necessary
			* Update to newer versions of Kubernetes with no downtime

**GKE organization**
		* Container cluster
			* Group of Compute Engine instances running Kubernetes
			* Contains 1 or more node instances and managed Kubernetes master endpoint
			* Central foundation of GKE
					* Nodes, pods, services, and replication controllers all run within cluster

		* Kubernetes master
					* Manages the cluster
					* Single endpoint for interacting with your cluster

		* Nodes
					* Individual Compute Engine instances
					* Run services to support Docker containers
					* Each node contains one or more pod
		* Pods
					* Group of one or more containers
					* Pods share storage and configuration data relating to those containers
					* Pods can contain multiple containers, and multiple pods can exist on each node
					* Pods have a short lifespan, and can be deleted and recreated as necessary
		* Replication controller
					* Ensures the requested number of pod replicas are always available and running at a given time
					* Automatically adds or removes pods as required to maintain a desired state.

	* Services
					* Defines a logical set of pods across nodes and a way to access them using single IP address and port number
					* Services create an abstraction layer that decouples frontend clients from pods that provide backend functions. In this way, clients can work without concerns about which pods are being created and deleted at any given moment.
	* Container Registry
					* Not part of the Container cluster, but a separate service
					* Secure, private Docker image storage for deployments
					* Push container images to registry for deployment to GKE, GCE, or your own hardware

- - - -

#cloud/gcloud/architect_exam