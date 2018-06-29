# Introduction to GCP 
##### Why choose Google Cloud Platform?
	* What is Google Cloud Platform?
		* Suite of cloud computing services
		* Google’s worldwide collection of data centers
		* Hosts IaaS, PaaS, and SaaS use cases
		* At a basic level, it hosts and manages your computer 				infrastructure so you don’t have to

##### Like most other cloud platforms:
	* “Pay-as-you-go” basis, use only what you need
		* Also known as ‘on demand’ computing
	* Convert capital expenses into operating expenses
	* Focus on rapid innovation
	* Productivity enhanced due to no software installed
	* “Vertically integrated” stacks enhance functionality, performance, reliability, and security

##### What makes GCP stand out?
	* Access the same infrastructure Google uses for their own services
	* Customer friendly pricing (https://cloud.google.com/pricing)
		* Compute Engine instances billed per minute, not hour
		* Automatic sustained use discounts – no upfront commitment required
		* Archive coldline storage for extremely cheap
	* Private Global Fiber Network
		* Blazing fast
		* Data moving between data centers never leaves the private network
	* Live migration of Virtual Machines
	* Better performance
		* Website benchmarks showed as much as 50% improvement in loading speed
		* Instantly scalable. VM’s can auto-scale without shutting machine down.
		* Access to GPU’s for high end scientific computing and machine learning
	* Industry leading security
		* Over 500 full time security professionals
		* All data encrypted in transit and at rest
		* Expansive audit compliance list
		* SSAE16, ISO 27
		* 017, ISO 27018, PCI, and HIPAA
	* Access to innovative resources not available anywhere else
		* Big Data, Machine Learning
		* API’s (Video Intelligence, Maps)
		* “Build what’s next”
- - - -
# # Data Center Infrastructure
##### How is GCP built?
	* Data Centers
		* Google operates an extensive deployment of high-efficiency backend data centers used for computation and storage capacity.
	* Backbone
		* Google has built a global, meshed backbone network to connect their data centers and to deliver traffic to their edge points of presence (POPs).
	* Points of Presence
		* 90 + edge points of presence in 33 countries connected via Google’s backbone network.
	* Edge Caching
		* Google runs an edge caching platform on top of their network infrastructure with edge locations in virtually every country.
	* Cloud Regions and Zones
		* Nine regions split into 27 zones
	* Regions
		* Regions are specific geographical locations where you can run your resources
		* Collections of zones
		* Regional resources are available to resources in any zone in the region
		* Frequently expanding
	* Zones
		* Isolated physical locations within a region
		* Zonal resources are only available in that zone
		* Machines in different zones have no single point of failure
		* For example: an effective disaster recovery plan would have assets deployed across multiple zones, or even different regions.
	* Commitment to environmental responsibility
		* 100% renewable energy
		* Extremely efficient infrastructure
		* Optimized to run within Google’s environment
		* Carbon neutral since 2007
		* Hosting company resources on GCP is more environmentally friendly than hosting your own server resources
		* Learn more at https://www.google.com/about/datacenters/
##### Network infrastructure from data centers to end users
		* Three elements:
			* Core data centers
			* Edge Points of Presence (PoPs)
			* Edge nodes
##### Points of Presence
	* 90+ locations worldwide
	* Brings Google traffic closer to users worldwide, thereby reducing their costs and providing users with a better experience.
	* Connects to the private meshed network backbone that connects Edge PoPs to data centers, and bridges to the public Internet 
	
##### Edge Nodes
	* Tier of Google’s infrastructure closest to end users
	* Internet service providers (ISP’s) deploy Google-supplied servers inside their own network
	* “Static content that is very popular with the local host’s user base, including YouTube and Google Play, is temporarily cached on edge nodes. Google’s traffic management systems direct user requests to an edge node that will provide the best experience.”
	* Pulling popular content from edge cache is substantially faster than pulling everything from data centers

##### End result
	* Fast, redundant, worldwide presence that provides fast and reliable access to your resources no matter where in the world you are
	* All of this while being 100% carbon neutral
		
#cloud/gcloud/architect_exam