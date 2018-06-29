# GCP_Big_Data_and_Machine_Learning
- - - -
# What is Big Data, and why is it important?
	* Extremely large data sets that may be analyzed computationally to reveal patterns, trends, and associations, especially relating to human behavior and interactions.

	* Big data refers to data that would typically be too expensive to store, manage, and analyze using traditional (relational and/or monolithic) database systems. Usually, such systems are cost-inefficient because of their inflexibility for storing unstructured data (such as images, text, and video), accommodating “high-velocity” (real-time) data, or scaling to support very large (petabyte-scale) data volumes. 

	* For this reason, the past few years has seen the mainstream adoption of new approaches to managing and processing big data, including Apache Hadoop and NoSQL database systems.

**Where does big data come from?**

	* In the past, most customer data came from structured formats (e.g. bank transactions). Today, the large amount of data that organizations create daily in the form of unstructured online customer interactions completely dwarfs the past structured data formats from just a few years ago.

	* One big source is the ‘Internet of Things’ (IoT) of interconnected devices and sensors, which has created an exponential increase in the sheer volume of data as text, images, video, and audio.

	* Also, in some regulated industries, data that in the past would be deemed unimportant and archived now needs to be accessible and analyzed for compliance reasons.

**Why is big data important?**
	* Business value

		* The ability to get business value out of this mass of data on a consistent basis is now a trait of successful organizations across every industry
		* In some industries such as advertising and retail, it’s literally a matter of survival

	* If you can get more data, and if you can properly act on that data, the more value you will receive

	* Big data often goes hand in hand with machine learning, as more data can ‘train’ big data models to get even more value.

**Why the cloud is the best platform for big data**

	* Today’s big data needs often prove to be complex to deploy, manage, and use in an on-premise situation. The space, costs, and administration requirements necessary to maintain them are high.

	* Managed big data services (like BigQuery and Machine Learning Engine) reduce cost and reduce the complexities of hosting your own system 
			* Offers the ability to experiment with different products/systems without the up front cost

**How does GCP do big data well?**
	* Big data analytics at Google scale
			* Able to store and process the sheer volume of data
			* Big data is in their DNA
	* Serverless, managed infrastructure
			* All backend infrastructure handled for you, including autoscaling
	* Fast action on petabyte sized datasets
	* Both batch and stream processing
	* Spark and Hadoop in the cloud
	* Industry leading Machine Learning capabilities

# GCP Big Data services
**Google BigQuery**
		* Google BigQuery is an enterprise data warehouse that stores and queries massive datasets (100’s of terabytes) by enabling super-fast SQL queries using the processing power of Google’s infrastructure. 
		* BigQuery replaces the typical hardware setup for a traditional data warehouse and serves as a collective home for all analytical data in an organization.
		* BigQuery is fully-managed. You don’t need to deploy any resources, such as disks and virtual machines. 
		* Real time analysis - Real-time analytics is the use of, or the capacity to use, data and related resources as soon as the data enters the system.

**Google Cloud Dataflow**
		* Fully managed data processing service
				* No resource provisioning – on demand and nearly limitless capacity
		* Batch and stream processing
				* Batch = process large volume of data at once (e.g. all data from past week)
				* Stream = continuous input and output of data
						* Fast turn-around of data
		* Open source – no vendor lock in
		* Tight integration with rest of GCP

**Google Cloud Dataproc**

		* Cloud Dataproc is a fast, easy-to-use, fully-managed cloud service for running Apache Spark and Apache Hadoop clusters in a simpler, more cost-efficient way.
		* Scalable clusters - quickly create and resize clusters as needed

**Google Cloud Datalab**

		* Cloud Datalab is a powerful interactive tool created to explore, analyze, transform and visualize data and build machine learning models on Google Cloud Platform. It runs on Google Compute Engine and connects to multiple cloud services easily so you can focus on your data science tasks.
		* Open source – built on Jupyter (formerly iPython)
		* Integrates with other GCP services
		* Supports machine learning models based on TensorFlow

**Google Cloud Dataprep**

		* Google Cloud Dataprep is an intelligent data service for visually exploring, cleaning, and preparing structured and unstructured data for analysis. Cloud Dataprep is serverless and works at any scale. There is no infrastructure to deploy or manage. Easy data preparation with clicks and no code.

**Google Cloud Pub/Sub**

		* Google Cloud Pub_Sub brings the scalability, flexibility, and reliability of enterprise message-oriented middleware to the cloud. By providing many-tomany, asynchronous messaging that decouples senders and receivers, it allows for secure and highly available communication between independently written applications. Google Cloud Pub_Sub delivers low-latency, durable messaging that helps developers quickly integrate systems hosted on the Google Cloud Platform and externally.
		* Send and receive messages between messages in real time
		* Ideal for stream processing
		* Connecting service between other GCP services
		* Decouples senders and receivers
		* Dependable communication between independently written apps
		* For example, a residential sensor can stream data to backend servers hosted in the cloud.
- - - -

#cloud/gcloud/architect_exam