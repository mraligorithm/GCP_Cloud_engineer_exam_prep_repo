# GCP_Storage_Options 
- - - -
#### Storage Options Overview
**Google Storage Options = ‘store data here’**
**Several storage options available on GCP**
	* What format is our data? - breakdown
			* Structured vs non-structured
			* Structured = table format - columns and rows = database options
			* Non-structured = Google Cloud Storage
	
	* Database options are broken down further:
			* Relational = SQL
			* Non-Relational = NoSQL
			* Can be VERY roughly defined as NoSQL for scale, SQL for consistency
			* SQL = CloudSQL
			* NoSQL = Datastore, Bigtable
			* Further broken down into whether running analytics, BigTable for analytics, Datastore for not

	* New category in Spanner
		* Previously used internally at Google, not released for everyone else to use
		* Like SQL, it is a relational database
		* Claims advantages of both SQL and NoSQL, called ‘NewSQL’

	* Cloud Storage
		* Has no knowledge of the structure/order of data that you put in, it just stores it for you as requested regardless of internal structure we set.
				* Files referred to as ‘objects’.

**BigQuery = both a storage and analysis/analytics service**
**CloudSQL**
		* Create instance_region_size
		* Database version
			* Select MySQL version
			* Hosted MySQL service, not similar to MySQL, it IS MySQL
		* Low maintenance MySQL instance
			* OS management/updates handled for you
		* Limited scalability

**NoSQL Options**
**Datastore**
		* Born as an App Engine data repository, but now works outside of it
		* Scale and flexible
		* Fast and loose (flexible)
		* No provisioning resources, true NoOps
		* Scales from 0 to TB’s of data
**BigTable**
		* Hosted version of Google’s own internal BigTable tech
		* HBase was born from BigTable
		* Managed service
		* For:
			* Storing over a TB of structured data
			* Very high volume of writes
			* Read/write latency in single digit millisecond range with high consistency
			* Easy migration from HBase to a managed cloud service
		* Since so low-latency, entire database stored in single zone
		* More nodes = more data throughput (and more cost)
		* Nodes cost per hour, whether used or not
		* Super high scaling
		* For big applications/data only. Overkill for smaller applications (minimum nodes) from cost perspective
**Above 3 databases are OPERATIONAL - intended to be part of an application**
**BigQuery - analytical database, not operational**
		* Run SQL queries on TB’s of data in seconds
#cloud/gcloud/architect_exam