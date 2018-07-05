# GCP-VPC-Core-Concenpts 
- - - -
In this concept we will be covering the core concepts of VPC on Google cloud platform
- - - -
A VPC network, sometimes just called a “network,” is a virtual version of a physical network, like a data center network. It provides connectivity for your Compute Engine virtual machine (VM) instances, Kubernetes Engine clusters, App Engine Flex instances, and other resources in your project.

__Projects can contain multiple VPC networks.__ New projects start with a default network that has one subnet in each region (an auto mode network).
- - - -
#### VPC network example
The following example illustrates custom mode network with three subnets in two regions:

![](GCP-VPC-Core-Concenpts/Screen%20Shot%202018-07-05%20at%208.44.10%20AM.png)


		* Subnet1 is defined as 10.240.0.0/24 in the us-west1 region.
			* Two VM instances in the us-west1-a zone are in this subnet. Their IP addresses both come from the available range of addresses in subnet1.
	* Subnet2 is defined as 192.168.1.0/24 in the us-east1 region.
		* Two VM instances in the us-east1-a zone are in this subnet. Their IP addresses both come from the available range of addresses in subnet2.
	* Subnet3 is defined as 10.2.0.0/16, also in the us-east1 region.
		* One VM instance in the us-east1-a zone and a second instance in the us-east1-b zone are in subnet3, each receiving an IP addresses from its available range. Because subnets are regional resources, instances can have their network interfaces associated with any subnet in the same region that contains their zones.

- - - -
## Specifications
VPC networks have the following properties:

		* VPC networks, including their associated routes and firewall rules, are global resources. They are not associated with any particular region or zone. 

		* Subnets are regional resources. Each subnet defines a range of IP addresses. For more information about networks and subnets, see networks and subnets.

		* Traffic to and from instances can be controlled with network firewall rules.

		* Resources within a VPC network can communicate with one another using internal (private) IPv4 addresses, subject to applicable network firewall rules. For more information, see communication within the network.

		* Instances with only private IP addresses can communicate with Google APIs and services if you enable Private Google Access for the subnets in which they reside.

		* Network administration can be secured using Identity and Access Management (IAM) roles.

		* An organization can use Shared VPC to keep a VPC network in a common host project. Authorized IAM members from other projects in the same organization can create resources that use subnets of the Shared VPC network.

		* VPC networks can be connected to other VPC networks in different projects or organizations by using VPC Network Peering.

		* VPC networks can be securely connected in hybrid environments using Cloud VPN or Google Cloud Interconnect.

		* VPC networks only support IPv4 unicast traffic. They do not support broadcast, multicast, or IPv6 traffic within the network. However, IPv6 can be used to reach resources in the network. For example, IPv6 addresses can be assigned to a global load balancer, and the App Engine standard environment supports IPv6.

		* VPC networks use a maximum transmission unit (MTU) of 1,460 bytes. This MTU value is offered to instances via DHCP option 26 per RFC 2132. Larger MTUs, including those associated with jumbo frames, are not supported. Configuring an MTU of larger than 1460 can lead to packet loss.

- - - -

#### Internet access requirements

The following criteria must be satisfied for an instance to have outgoing Internet access:

		* The network must have a valid default Internet gateway route or custom route whose destination IP range is the most general (0.0.0.0/0). This route simply defines the path to the Internet. See Routes for more information about routes.
		* Firewall rules must allow egress traffic from the instance. Unless overridden by a higher priority rule, the implied allow rule for egress traffic applies to all instances in the network.
		* One of the following must be true:
			* The instance must have an external IP address. An external IP can be assigned to an instance when it is created or after it has been created.

			* Another instance in the network must serve as as a NAT gateway.

- - - -

####  Firewall Rules Overview

Google Cloud Platform (GCP) firewall rules let you allow or deny traffic to and from your virtual machine (VM) instances based on a configuration you specify. GCP firewall rules are applied at the virtual networking level, so they provide effective protection and traffic control regardless of the operating system your instances use.

Every VPC network functions as a distributed firewall. While firewall rules are defined at the network level, connections are allowed or denied on a per-instance basis. You can think of the GCP firewall rules as existing not only between your instances and other networks, but between individual instances within the same network.

#### Firewall rules in GCP

GCP firewall rules are specific to a VPC network. Each rule either allows or denies traffic when its conditions are met. Its conditions allow you to specify the type of traffic, such as ports and protocols, and the source or destination of the traffic, including IP addresses, subnets, and instances. Refer to firewall rule components for descriptions of the components that define a firewall rule.

Every network has two permanent implied firewall rules which permit outgoing connections and block incoming connections. Refer to the default and implied firewall rules section for more information about their applicability and how they interact with rules you define. Additionally, the default network is pre-populated with some additional editable rules.

You create or modify GCP firewall rules through the Google Cloud Platform Console, gcloud command line tool, and REST API. When you create or modify a firewall rule, you can specify the instances to which it is intended to apply by using the target component of the rule.

#### Specifications
###### Firewall rules have the following characteristics:

	1. Firewall rules are defined at the VPC network level, and are specific to the network in which they are defined. The rules themselves cannot be shared among networks.
	
	2. Firewall rules only support IPv4 traffic. When specifying a source for an ingress rule or a destination for an egress rule by address, you can only use an IPv4 address or IPv4 block in CIDR notation.
	
	3. The action taken by a firewall rule is either allow or deny. The rule cannot simply log as an action. Refer to the action on match component of a firewall rule for more information.
	
	4. There is no logging mechanism for firewall rules.

	5. Each firewall rule is defined to apply to either incoming (ingress) or outgoing (egress) traffic, not both. Refer to the direction of traffic component of a firewall rule for more information.
	
	6. GCP firewall rules are stateful. If a connection is allowed between a source and a target or a target and a destination, all subsequent traffic in either direction will be allowed. In other words, firewall rules allow bidirectional communication once a session is established. Firewall rules cannot allow traffic in one direction while denying the associated return traffic.

	7. GCP firewall rules do not reassemble fragmented TCP packets. Consequently, a firewall rule applicable to the TCP protocol can only apply to the first fragment because it contains the TCP header. Firewall rules applicable to the TCP protocol do not apply to the subsequent TCP fragments.

	8. The maximum number of tracked connections in the firewall rule table depends on the number of stateful connections supported by the machine type of the instance:
![](GCP-VPC-Core-Concenpts/Screen%20Shot%202018-07-05%20at%208.56.16%20AM.png)




#cloud/gcloud/engineer_cert/GCP-DeepDive