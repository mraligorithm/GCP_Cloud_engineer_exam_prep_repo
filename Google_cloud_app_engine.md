# Google_cloud_app_engine
- - - -
# What is Platform as a Service (PaaS)?
	* Definition: PaaS is a category of cloud computing that provides a platform and environment to allow developers to build applications and services over the internet without having to worry about allocating and managing infrastructure.
	* Popular with software and web developers
	* Key distinctions vs. IaaS:
		* Focused on application development
		* Managed infrastructure
		* Pay per use vs. pay per allocation
		
# What is App Engine?
	* GCP’s tool to build modern web and mobile applications on an open cloud platform
	* App Engine is a fully managed application platform that allows developers to build web applications and API services without having to worry about lower-level infrastructure by abstracting away the infrastructure so you focus only on code
	* For an ‘out of the box’ environment with default configurations, App Engine supports Node.js, Java, Ruby, C#, Go, Python, and PHP
	* Open Tools that don’t lock users in: Developers shy away from proprietary tools that lock them into one platform (aka vendor lock in).
		* App Engine supports custom Docker images, letting developers bring their own custom software stack, making it easy to migrate their application to a different platform.
		* Per Google engineer on vendor lock in: “it’s not our strategy – in fact we actively work to minimize it.”

**Simply defined:**
	* You bring your code, Google handles the rest.

**What does this look like in practice?**
	* With traditional physical infrastructure, you need to manage:
		* firewalls,
		* denial of service attacks
		* viruses
		* patches
		* network configurations,
		* failover
		* load balancing
		* capacity planning (scaling)
		* OS patches and upgrades (in particular security related)
		* hardware upgrades or fixes
		* certification levels
		* most security issues
		* Routing
		* IP addressing
	* IaaS solutions (like Compute Engine) help with several of the above aspects, but App Engine handles all of them for you

**App Engine environments: Standard vs. Flexible**
**Standard:**
		* The App Engine standard environment is based on container instances running on Google’s infrastructure. Containers are preconfigured with one of several managed available runtimes (Java 7, Java 8, Python 2.7, Go and PHP). Each runtime also includes libraries that support App Engine Standard APIs. For many applications, the standard environment runtimes and libraries might be all you need. 
		* The App Engine standard environment makes it easy to build and deploy an application that runs reliably even under heavy load and with large amounts of data. It includes the following features:
			* Persistent storage with queries, sorting, and transactions.
			* Automatic scaling and load balancing.
			* Asynchronous task queues for performing work outside the scope of a request.
			* Scheduled tasks for triggering events at specified times or regular intervals.
			* Integration with other Google cloud services and APIs.
		* Applications run in a secure, sandboxed environment, allowing App Engine standard environment to distribute requests across multiple servers, and scaling servers to meet traffic demands. Your application runs within its own secure, reliable environment that is independent of the hardware, operating system, or physical location of the server.

##### Flexible Environment
Based on Google Compute Engine, the App Engine flexible environment automatically scales your app up and down while balancing the load. Microservices, authorization, SQL and NoSQL databases, traffic splitting, logging, versioning, security scanning, and content delivery networks are all supported natively. In addition, the App Engine flexible environment allows
you to customize your runtime and even the operating system of your virtual machine using Dockerfiles.

		* Runtimes - The flexible environment includes native support for Java 8 / Servlet 3.1 / Jetty 9, Python 2.7 and Python 3.5, Node.js, Ruby, PHP, .NET core, and Go. Developers can customize these runtimes or provide their own runtime by supplying a custom Docker image or Dockerfile from the open source community.

		* Infrastructure Customization - Because VM instances in the flexible environment are Google Compute Engine virtual machines, you can take advantage of custom libraries, use SSH for debugging, and deploy your own Docker containers.

		* Performance - Take advantage of a wide array of CPU and memory configurations. You can specify how much CPU and memory each instance of your application needs and the flexible environment will provision the necessary infrastructure for you.

**App Engine manages your virtual machines, ensuring that:**
		* Instances are health-checked, healed as necessary, and co-located with other services within the project.
		* Critical, backwards compatible updates are automatically applied to the underlying operating system.
		* VM instances are automatically located by geographical region according to the settings in your project. Google’s management services ensure that all of a project’s VM instances are co-located for optimal performance.
		* VM instances are restarted on a weekly basis. During restarts Google’s management services will apply any necessary operating system and security updates.
		* You always have root access to Compute Engine VM instances. SSH access to VM instances in the flexible environment is disabled by default. If you choose, you can enable root access to your app’s VM instances.

**App Engine locations**
		* App Engine is regional, which means the infrastructure that runs your apps is located in a specific region and is managed by Google to be redundantly available across all the zones within that region.

**App Engine is available in the following regions:**
	* us-central1
	* us-east1
	* us-east4
	* europe-west1
	* europe-west2
	* Lasia-northeast1
	* Australia-southeast1
#cloud/gcloud/architect_exam