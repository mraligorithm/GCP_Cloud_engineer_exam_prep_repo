# Interacting_with_Google_Cloud_Platform
- - - -
**Three methods of interaction:**
		* Cloud Console - Web user interface
		* Cloud SDK/Cloud Shell (command line interface)
		* REST-based API

**GCP Console**
		* Easy access to all your Google Cloud Platform projects.
		* Access to the Google Cloud Shell.
		* A customizable project dashboard, with an overview of Google Cloud resources, billing, and a filterable activity listing.
		* Easy access to all Google Cloud Platform APIs, with a dashboard specific to each API, and access to manage your resources.
		* Links to Google Cloud Platform starting points, news, and documentation.

**Command line options**
		* Google Cloud SDK
		* Cloud Shell

**Cloud SDK**
		* Command line tools for GCP
		* manage resources and applications hosted on Google Cloud Platform.

**Cloud SDK provides the following tools:**
		* gcloud
		* bq
		* gsutil

**gcloud**

gcloud is a command-line tool that you can use to perform many common tasks on Google Cloud Platform. You can use gcloud to create and manage:

		* Google Compute Engine virtual machine instances and other resources
		* Google Cloud SQL instances
		* Google Container Engine clusters
		* Google Cloud Dataproc clusters and jobs
		* Google Cloud DNS managed zones and record sets
		* Google Cloud Deployment manager deployments

**bq**
bq is a command-line tool that you can use to work with data in Google BigQuery. You can use bq to manage datasets, tables and other entities in BigQuery, as well as run queries on your
data.

**gsutil**
gsutil is a command-line tool that you can use to perform tasks in Google Cloud Storage. You can use gsutil to:
		* Create and manage Cloud Storage buckets
		* Upload objects to buckets, and download and delete them
		* Move, copy and rename objects
		* Manage access to stored data

**Cloud Shell**
Google Cloud Shell is an interactive shell environment for Google Cloud Platform. It makes it easy for you to manage your projects and resources without having to install the Google Cloud SDK and other tools on your system. With Cloud Shell, the Cloud SDK gcloud command-line tool and other utilities you need are always available when you need them.

**Cloud Shell provides the following:**
		* A temporary Compute Engine virtual machine instance
		* Command-line access to the instance from a web browser
		* 5 GB of persistent disk storage
		* Pre-installed Google Cloud SDK and other tools
		* Language support for Java, Go, Python, Node.js, PHP and Ruby
		* Web preview functionality
		* Built-in authorization for access to Cloud Platform Console projects and resources


**Restful API’s**
		* Programmatic access to products and services
		* Typically use JSON as an interchange format
		* Use OAuth 2.0 for authentication and authorization
		* Enabled through the Google Cloud Platform Console
		* Most APIs include daily quotas and rates (limits) that can be raised by request
		* Important to plan ahead to manage your required capacity
		* Experiment with APIs Explorer

**APIs Explorer**
		* The APIs Explorer is an interactive tool that lets you easily try Google APIs using a browser

**With the APIs Explorer, you can:**
		* Browse quickly through available APIs and versions.
		* See methods available for each API and what parameters they support along with inline documentation.
		* Execute requests for any method and see responses in real time.
		* Make authenticated and authorized API calls with ease.
		* Support various languages
				* Java, Python, JavaScript, PHP, .NET, Go, Node.js, Ruby, Objective-C, Dart

**Cloud Shell Limitations**
		* 1 hour time out for inactivity
			* Machine will terminate/self-delete
			* $HOME directory contents will be preserved for new session
		* Direct interactive use only
			* Not for running high computational/network workloads
			* If in violation, session can be terminated without notice
		* For long periods of inactivity, home disk may be recycled (with advance notice via email)
			* If need longer inactive period, consider either local installed SDK or use Google Cloud Storage for long term storage

**Gcloud commands**
		* For Cloud Shell and local installed Google Cloud SDK
		* Manage Google Cloud Platform resources and developer workflow
		* (Typical) command format:
			* gcloud [GROUP] [GROUP] [COMMAND]—arguments
		* Examples:
`gcloud compute instances create instance-1 –zone us-central1-a`
`gcloud config set project my-unique-project-id`
Full gcloud command list at https://cloud.google.com/sdk/gcloud/reference/

# API Explorer
https://developers.google.com/apis-explorer
#cloud/gcloud/architect_exam