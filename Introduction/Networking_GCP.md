# Networking_GCP
- - - -
# Virtual Private Cloud (VPC) Network
A VPC network is a virtual version of the traditional physical networks that exist within and between physical data centers. A VPC network provides connectivity for your Compute Engine virtual machine (VM) instances, Container Engine containers, App Engine Flex services, and other network-related resources.

Each GCP project contains one or more VPC networks. Each VPC network is a global entity spanning all GCP regions. This global VPC network allows VM instances and other resources to communicate with each other via internal, private IP addresses.

Each VPC network is subdivided into subnets, and each subnet is contained within a single region. You can have more than one subnet in a region for a given VPC network. Each subnet has a contiguous private RFC1918 IP space. You create instances, containers, and the like in these subnets. When you create an instance, you must create it in a subnet, and the instance draws its internal IP address from that subnet.

Virtual machine (VM) instances in a VPC network can communicate with instances in all other subnets of the same VPC network, regardless of region, using their RFC1918 private IP addresses. You can isolate portions of the network, even entire subnets, using firewall rules.

**External IP addressing**
	* A static external IP address is an external IP address that is reserved for your project until you decide to release it. If you have an IP address that your customers or users rely on to access your service, you can reserve that IP address so that only your project can use it. It is also possible to promote an ephemeral external IP address to a static external IP address.

**Routes**
	* A route is a mapping of an IP range to a destination. Routes tell the VPC network where to send packets destined for a particular IP address.
	* By default, every network has routes that let instances in a network send traffic directly to each other, even across subnets. In addition, every network has a default route that directs packets to destinations that are outside the network. While these routes cover most of your normal routing needs, you can also create special routes that override these routes. For example, you could create a route that forwards packets destined for theInternet to a proxy server first.

**Firewall rules in GCP**
	* Every GCP network also functions as a managed, distributed firewall. While firewall rules are applied to the network as a whole, the connections are allowed or denied at the instance level. You can think of the firewall as existing not only between your instances and other networks, but between individual instances within the same network.

	* Unless you specify otherwise, GCP applies every rule to every instance in the given network. For example, a firewall rule that denies connections from a range of IP addresses will deny those connections for all instances in the network.

	* You can restrict which instances a rule applies to by using target tags. For example, you can create a firewall rule that allows only instances marked with a particular tag to reach certain IP ranges.

	* If all firewall rules in a network are deleted, there is still an implied “Deny all” ingress rule and an implied “Allow all” egress rule for the network.

**Cloud DNS**
	* DNS translates a computer domain names (like google.com) into IP addresses 
	* Google Cloud DNS is a high-performance, resilient, global Domain Name System (DNS) service that publishes your domain names to the global DNS in a cost-effective way.

	* Create managed zones
		* Add, edit, and delete DNS records

**Cloud VPN**
	* Google Cloud VPN securely connects your on-premises network to your Google Cloud Platform (GCP) Virtual Private Cloud (VPC) network through an IPsec VPN connection. Traffic traveling between the two networks is encrypted by one VPN gateway, then decrypted by the other VPN gateway. This protects your data as it travels over the Internet.

	* Supports site to site (gateway to gateway) connections, but not client-gateway connections.

**Cloud Router**
	* You can use use VPNs to securely connect your on-premises networks your VPC networks. Without Cloud Router, you are required to configure your VPNs using static routes. With Cloud Router, your Cloud VPNs support dynamic routing.
	* Cloud Router peers with your VPN gateway or router and exchanges topology information via BGP. Network topology changes propagate automatically between your VPC network and your on-premises network, thereby eliminating the need to configure static routes for your Cloud VPN tunnels.
	* Cloud Router is a fully distributed and managed Google cloud service that is architected using the principles of Software-Defined Networking (SDN) and delivered on Google’s software-defined network virtualization stack.

**Cloud Interconnect**
	* Connect your infrastructure to Google’s network edge with enterprise-grade interconnect Carrier Interconnect Connect to Google through carrier partners (7 as of now) - enterprise grade connections

	* Equinix, for example, will offer businesses up to a 10Gb connection to Google’s cloud services through its Cloud Exchange platform in 15 markets. Why does this matter? Many enterprises that want to move to the cloud want to be able to use these services similar to how they use their on-premise servers. To do that, they need a private network with a very fast connection to the cloud provider’s data centers and that’s what Google now offers them.

	* Direct Peering
		* developers can get a blazingly fast connection directly to Google’s servers in over 70 points of presence in 33 countries. With direct connect, customers can establish their own private links to Google without using an intermediary network.
		* Connect directly to edge network location
		* Works in 70+ locations in 33 countries

	* CDN Interconnect
		* Content Delivery Network - Helps your website to serve images faster and help improves load time.
	
- - - -

# Tools
**Stackdriver**
#### Monitoring, logging & diagnostics
	* Google Stackdriver provides powerful monitoring, logging, and diagnostics for cloud operations. By equipping you with insight into the health, performance, and availability of cloud-powered applications, enabling you to find and fix issues faster. It is natively integrated with Google Cloud Platform, Amazon Web Services, and popular open source packages. Stackdriver provides a wide variety of metrics, dashboards, alerting, logmanagement, reporting, and tracing capabilities.
	* Natively monitor GCP, AWS, or a hybrid of both environments
	* Combine metrics, logs, and metadata from both platforms into a single viewing environment
	* Partner ecosystem and tools to make working with Stackdriver even easier.
	* Partners include: PagerDuty, BMC, Splunk, and others.

##### Stackdriver Monitoring
	* Full-stack monitoring for Google Cloud Platform and Amazon Web Services.
##### Stackdriver Logging
	* Real-time log management and analysis.
##### Stackdriver Error Reporting
	* Identify and understand your application errors.
##### Stackdriver Debugger
	* Investigate your code’s behavior in production.
##### Stackdriver Trace
	* Find performance bottlenecks in production.
##### Google Cloud Deployment Manager
	* Infrastructure Management Service
		* specify all the resources needed for your application in a declarative format using yaml
		* yaml syntax lists each of the resources in your deployment
		* Repeatable Deployment Process
		* By creating configuration files which define the resources, the process of creating those resources can be repeated over and over with consistent results.
##### Declarative Language
	* Many tools use an imperative approach, requiring the user to define the steps to take to create and configure resources. A declarative approach allows the user to specify what the configuration should be and let the system figure out the steps to take.
	* Greatly simplifies the process
##### Focus on the Application
	* The user can focus on the set of resources which comprise the application or service instead of deploying each resource separately.

##### Template-Driven
	* Templates allow the use of building blocks to create abstractions or sets of resources that are typically deployed together (e.g. an instance template, instance group and autoscaler). These templates can used over and over by changing input values to define what image to deploy, the zone in which to deploy or how many virtual machines to deploy.

##### Google Cloud Source Repositories
	* Git repository hosted on GCP
	* Google Cloud Source Repositories provides Git version control to support collaborative development of any application or service, including those that run on Google App Engine and Google Compute Engine. When paired with Stackdriver Debugger, you can use Cloud Source Repositories and other tools to view debugging information along with code during application runtime. Cloud Source Repositories also provides a source browser to view your repository files from within the Cloud Console.

	* Connect to GitHub or Bitbucket
	* Built in Source Code Editor
	* Integrates with Stackdriver debugger
	
- - - -

#cloud/gcloud/architect_exam