2025-05-22 13:29

Status: #new 

Tags: [[AWS Cloud Practitioner]]

# AWS Cloud Practitioner Essentials
## Module 1: Introduction to AWS

### What is Cloud Computing
Definition: On-demand delivery of IT resources and applications through the internet with pay-as-you-go pricing
### Client-Server Model
- **Client**: a web browser or desktop app that person interacts to make requests to computer servers
- **Server**: services, such as Amazon Elastic Compute Cloud (Amazon EC2) -  a type of virtual server
Example: A **client** makes a request for a new article, the **server** evaluates the details of this request and fulfils it by returning the info to the client

### Deployment models for cloud computing
- **Cloud-Based**
	- Run all parts of the app in the cloud
	- Migrate existing apps to the cloud
	- Design and build new apps in the cloud
	- Example: A company might create an app consisting of virtual servers, databases, and networking components that are fully based in the cloud
- **On-Premises**
	- Deploy resources by using virtualization and resource management tools
	- Increase resource utilization by using app management and virtualization technologies
	- Aka private cloud deployment
	- Example: Applications that run on technology that is fully kept in your on-premises data centre. The model might be similar to legacy IT infrastructure, however it's incorporation of application management and virtualization technologies helps to increase resource utilitsation.
- **Hybrid**
	- Connect cloud-based resources to on-premises infrastructure.
	- Integrate cloud-based resources with legacy IT applications.
	- Example: Some legacy apps are better maintained on prem or government regulations requires your business to keep certain records on premises.
		- With hybrid deployment, the company would be able to keep the legacy apps on prem while benefiting from the data and analytics services that run in the cloud.



## Module 2: Compute in the Cloud

### Amazon Elastic Compute Cloud (Amazon EC2)
Provides secure, resizable computer capacity in the cloud as Amazon EC2 instances.

With an Amazon EC2 instance you can use a virtual server to run applications in the AWS Cloud.

- You can provision and launch an Amazon EC2 instance within minutes.
- You can stop using it when you have finished running a workload.
- You pay only for the compute time you use when an instance is running, not when it is stopped or terminated.
- You can save costs by paying only for server capacity that you need or want.

### How Amazon EC2 works:
1. **Launch**: First launch an instance. Begin by selecting a template with basic configuration for your instance. These configurations include the OS, application server, or applications. You also select the instance type, which is the specific hardware configuration of your instance. You can also specify security settings to control the network traffic that can flow into and out of your instance.
2. **Connect**: Connect to the instance. Your programs and apps have multiple different methods to connect directly to the instance and exchange data. Users can also connect to the instance by logging in and accessing the computer desktop.
3. **Use**: After connecting to the instance, you can begin using it. You can run commands to install software, add storage, copy and organize files, and more.

### Amazon EC2 instance types
EC2 instance types are optimized for different tasks. When selecting an instance type, consider the specific needs of your workloads and applications. There are a few instance types:
#### General purpose instances
Provides a **balance of compute, memory, and networking resources**. You can use them for variety of workloads, such as:
- application servers
- gaming servers
- backend servers for enterprise applications
- small and medium databases

#### Compute optimized instances
Ideal for compute-bound applications **that benefit from high-performance processors.** Like general purpose instances, you can use compute optimized instances for workloads such as web, applications, and gaming servers

**Ideal for:**
- high-performance web servers
- compute-intensive application servers
- dedicated gaming servers
- batch processing workloads that require processing many transactions in a single group.

#### Memory optimized instances
Designed to deliver fast performance for **workloads that process large datasets** **in memory.** In computing, memory is a temporary storage area. It holds al the data and instructions that a CPU needs to be able to complete actions. Before a program or app is able to run, it is loaded from storage into memory. This preloading process gives the CPU direct access to the computer program.

An example scenario would be a workload that requires large amounts of data to be preloaded before running an application. This scenario might be a high-performance database or a workload that involves performing real-time processing of a large amount of unstructured data. 

#### Accelerated computing instances
Use hardware accelerators, or coprocessors, to perform some functions more efficiently than is possible in software running on CPUs.

Examples of these functions:
- **floating-point number calculations**
- **graphics processing**
- **data pattern matching**

A hardware accelerator is a component that can expedite data processing. Accelerated computing instances are ideal for workloads such as graphics applications, game streaming, and app streaming

#### Storage optimized instances
Designed for workloads that require **high, sequential read and write access to large datasets on local storage.**

Examples of workloads: 
- distributed file systems
- data warehousing apps
- high-frequency online transaction processing (OLTP) systems

term input/output operations per second (IOPS) is a metric that measures the performance of a storage device. It indicates how may different input or output operations a device can perform in 1 second. Storage optimized instances are designed to deliver tens of thousands of low-latency, random IOPS to apps

Input operations can be thought of as data put into a system, such as records entered into a database.

An output operation is data generated by a server. Example of output might be the analytics performed on the records in a database. If you have an app that has high IOPS requirement, a storage optimized instance can provide better performance over other instance types not optimized for this kind of use case.

### Amazon EC2 pricing
Pay only for the compute time that you use. The types are:
#### On-Demand
- ideal for short-term, irregular workloads that cannot be interrupted. 
- No upfront costs or minimum contracts apply. 
- Instances run continuously until you stop them, and you pay only for the compute time you use.

#### Reserved Instances
a billing discount applied to the use of On-Demand instances in your account. There are 2 available types of Reserved Instances:
- Standard Reserved Instances
- Convertible Reserved Instances

You can purchase these 2 for a 1-year or 3-year term with greater cost saving for the 3 year plan

**Standard Reserved Instances**
A good fit if you know the EC2 instance type and size you need for your steady-state applications and in which AWS Region you plan to run them. Reserved instances require you to state the following qualifications:
- **Instance type and size**: Example, m5.xlarge
- **Platform description (operating system):** Example, Microsoft Windows Server or Red Hat Enterprise Linux
- **Tenancy**: Default tenancy or dedicated tenancy

There is an option top specify an Availability Zone for your EC2 Reserved Instances. If this specification is made, you can get EC2 capacity reservation. This ensures that your desired amount of EC2 instances will be available when you need them

**Convertible Reserved Instances**
Appropriate for running EC2 instances in different Availability Zones or different instance types. You trade in a deeper discount when you require flexibility to run your EC2 instances

At the end of a Reserved Instance term, you can continue using the EC2 instance without interruption. However, you are charged On-Demand rates until you do one of the following:
- Terminate the instance
- Purchase a new Reserved Instance that matches the instance attributes (instance family and size, Region, platform, and tenancy)

#### EC2 Instance Savings Plans
These reduce EC2 instance costs when you make an hourly spend commitment to an instance family and Region for 1 or 3 year terms.
This term commitment results in savings of up to 72% compared to On-Demand rates. Any usage up to the commitment is charged at the discounted Savings Plans rate(for example, $10 per hour). Any usage beyond the commitment is charged at regular On-Demand rates

Benefits:
- Gives flexibility in EC2 usage over the duration of the commitment term
- Saving costs on running any EC2 Instance within an EC2 instance family in a chose Region (For example, M5 usage in N.Virginia) regardless of Availability Zone, instance size, OS or tenancy
- Similar to the savings in Standard Reserved Instances

Unlike Reserved Instances, you do not need to specify up from what EC2 instance type and size (for example, m5.large), OS, and tenancy to get a discount. You also don't need to commit to a certain number of EC2 instances over a 1 or 3 year term. Additionally, the EC2 Instance Savings Plan don't include an EC2 capacity reservation option.

You can use AWS Cost Explorer to visualise, understand and manage AWS costs and usage over time. The AWS Cost Explorer will analyse your EC2 usage over the past 7,30 or 60 days and provide customized recommendations based on it.

#### Spot Instances
Ideal for workloads with flexible start and end times, or that can withstand interruptions.
Use unused EC2 computing capacity and offer you cost savings up to 90% off of On-Demand prices.

Example:
A background processing job that can start and stop as needed  (such as the data processing job for a customer survey). You want to start and stop the job without affecting the overall operations of your business.

If you make a Spot request and EC2 capacity is available, you Spot Instance launches.
However, if you make a Spot request and EC2 capacity is unavailable, the request is not successful until the capacity becomes available. This unavailable capacity might delay the launch of your background processing job.

After launching a Spot Instance, if capacity is no longer available or demand for Spot Instances increases, your instance may be interrupted. This might not pose any issues for your background processing job.

However, in something like developing and testing apps, you would most likely want to avoid unexpected interruptions.

#### Dedicated Hosts
Physical servers with EC2 instance capacity that is fully dedicated to your use

You can use your existing per-socket, per-core, or per-VM software licenses to help maintain license compliance.

 You can purchase On-Demand Dedicated Hosts and Dedicated Hosts Reservations. Of all the Amazon EC2 options that were covered, Dedicated Hosts are the most expensive.

### Scaling Amazon EC2

#### Scalability 
Scalability involves beginning with only the resources you need designing your architecture to automatically respond to changing demand by scaling out or in.
As a result you pay for only the resources you use. You don't have to worry about a lack of computing capacity to meet you customers' needs.

#### EC2 Auto Scaling
Enables you to automatically add or remove EC2 instances in response to changing application demand. By automatically scaling your instances in and out as need, you can maintain a greater sense of app availability. There are 2 approaches:
- **Dynamic scaling** responds to changing demand
- **Predictive scaling** automatically schedules the right number of EC2 instances based on the predicted demand
![[EC2 Auto Scaling.png]]
To scale faster, we can use dynamic and predictive scaling together.

Example:
![[Auto Scaling Group.png]]
By adding EC2 Auto Scaling to an app, you can add new instances to the app when necessary and terminate them when no longer needed. 

The **minimum capacity** is the number of EC2 instances that launch immediately after you have created the Auto Scaling group. Here it is 1.

The **desired capacity** here is 2. If not desired number is specified, the desired capacity defaults to your minimum capacity

The **maximum capacity** here is 4. When demand is increased the Auto Scaling group will scale out but only to a max of 4 EC2 instances.

### Directing Traffic with Elastic Load Balancing
#### Elastic Load Balancing
An AWS service that automatically distributes incoming app traffic across multiple resources, such as EC2 Instances

A Load Balancer:
- Acts as a single point of contact for all incoming web traffic to your Auto Scaling group
- So when you add or remove EC2 instances in response to the amount of incoming traffic, these requests route to the load balancer first. Then, the requests spread across multiple resources that will handle them.
- Example: If you have multiple EC2 instances, Elastic Load Balancing distributes the workload across the multiple instances so that no single instance has to carry the bulk of it.

Although ELB and EC2 Auto Scaling are separate services, they work together to help ensure that apps running in EC2 can provide high performance and availability 

### Messaging and Queuing
#### Monolith applications and microservices
**Monolith**
- Tightly coupled components 
- If a single component fails, other components fail, and possibly the entire app fails

**Microservices**
- Application components are loosely coupled. 
- If a single component fails, other components continue to work because they are communicating with each other
- Loose coupling prevents the entire app from failing
- When designing on AWS, a microservice approach is good. 2 services that facilitate app integration are Amazon Simple Notification Service (Amazon SNS) and Amazon Simple Queue Service (Amazon SQS)

#### Amazon Simple Notification Service (Amazon SNS)
Is a publish/subscribe service. Using SNS topics, a publisher publishes messages to subscribers. This is similar to the coffee shop; the cashier provides coffee orders to the barista who makes the drinks.
In Amazon SNS, subscribers can be:
- web servers
- email addresses
- AWS Lambda functions
- or several other options
Example: A newsletter that can personalized to cater to specific needs. A newsletter that has things such as promos, events and new items. A subscriber can subscribe to one or more of these things without being forced to subscribe to all of them
#### Amazon Simple Queue Service (Amazon SQS)
Is a message queuing service. Using Amazon SQS, you can send, store and receive messages between software components, without losing messages or requiring other services to be available.

Example: Instead of a cashier given orders directly to a barista (which could cause problems when the barista is busy or away) the order can go to a queue (order board)

### Additional Compute Services
#### Serverless Computing
EC2 is a service that lets you run virtual servers in the cloud, which means you still have to manage it while your app is running. 
**Serverless** means that your code runs on servers, but you do not need to provision or manage these servers. 
Benefits of Serverless Computing:
- Innovate new products
- Not focus on server maintenance
- Flexibility to scale serverless applications
- Can adjust the applications' capacity by modifying the units of consumptions, such as throughput and memory
An AWS Service for serverless computing is **AWS Lambda**

#### AWS Lambda
A service that lets you run code without needing to provision. 

Benefits:
- Only pay for the compute time that you consume.
- Charges apply only when your code is running.
- Run code for virtually any type of app or backend service, with zero administration
Example: a simple Lambda function might involve automatically resizing uploaded images to the AWS Cloud. In this case, the function triggers when uploading a new image.

How AWS Lambda Works:
![[How AWS Lambda works.png]]
1. You upload code to Lambda
2. You set your code to trigger from an event source, such as AWS services, mobile apps, or HTTP endpoints
3. Lambda runs your code only when triggered
4. You would only pay for the compute time used to run code.

#### Containers
Provide a standard way to package your app's code and dependencies into a single object. 
Used for processes and workflows in which there are essential requirements for security, reliability, and scalability

#### AWS Elastic Container Service (Amazon [[ECS]])
A highly scalable, high-performance container management system that enables you to run and scale containerized apps on AWS. 

ECS supports Docker containers. Docker is a Software platform that enables you to build, test and deploy apps quickly. AWS supports the use of open-source Docker Community Edition and subscription-based Docker Enterprise Edition.
With ECS, you can use API calls to launch and stop Docker-enabled apps

#### Amazon Elastic Kubernetes Service (Amazon EKS)
A fully managed service that you can use to run Kubernetes on AWS.

Kubernetes is open-source software that enables you to deploy and manage containerized apps at a scale. 

#### AWS Fargate
A serverless compute engine for containers. It works with both ECS and EKS

When using Fargate, you do not need to provision or manage servers. Fargate manages your server infrastructure for you. You can focus more on innovating and developing your apps, and you pay only for the resources that are required to run your containers

## Module 3: Global Infrastructure and Reliability
### AWS Regions
When selecting a region for your services, data and apps, consider the 4 business factors:
1. Compliance with data governance and legal requirements
	- Depending on your company and location, you might need to run your data out of specific areas.
	- Example, if all the data needs to reside within the boundaries of the UK, you would choose the London region
2. Proximity to Customers
	- A region that is closer to customers help you get content to them faster
	- Example: A company in Washington, DC, USA has customers that live in Singapore. You should run your infrastructure in the Northern Virginia Region and run your apps in the Singapore region.
3. Available services within a Region
	- The closet region might not have all the features that you want to offer to a customer
	- Example: Amazon Braket (AWS quantum computing platform) might only be available in Singapore and only is in the USA.
4. Pricing
	- Different countries might have more expensive tax structures
	- Example, Brazil costs 50% more to run the same workload compared to the USA

#### Availability Zones
Is a single data centre or a group of data centres within a Region. Availability Zones are located tens of miles apart from each other. This is close enough to have low latency between Availability Zones. However, if a disaster occurs in one part of the Region, they are distant enough to reduce the chance that multiple Availability Zones are affected.

Example:
EC2 instance in a single Availability Zone
![[EC2 instance in a single Availability Zone.png]]
If us-west-1a were to fail, you would lose your instance

EC2 instances in multiple Availability Zones
![[EC2 instances in multiple Availability Zones.png]]
Best practice is to run apps across atleast 2 Availability Zones in a Region.

### Edge Locations
An edge location is a site the Amazon CloudFront uses to store cached copies of your content closer to your customers for faster delivery

![[Edge Locations.png]]
1. Suppose that your company's data is stored in Brazil, and you have customers who live in China. To provide content to these customers, you don’t need to move all the content to one of the Chinese Regions.
2. Instead of requiring your customers to get their data from Brazil, you can cache a copy locally at an edge location that is close to your customers in China.
3. When a customer in China requests one of your files, Amazon CloudFront retrieves the file from the cache in the edge location and delivers the file to the customer. The file is delivered to the customer faster because it came from the edge location near China instead of the original source in Brazil.
#### Amazon Cloudfront
- A global content delivery service.
- Uses a network of edge locations to cache content and deliver it to customers all over the world.
- When content is cached, it is stored locally as a copy.
### How to Provision AWS Resources
#### Ways to interact with AWS Services
- AWS Management Console
	- A manual tool
	- A web-based interface for accessing and managing AWS services. 
	- You can quickly access recently used services and search for other services by name, keyword, or acronym.
	- The console includes wizards and automated workflows that can simplify the process of completing tasks.
	- The AWS Console mobile app
- AWS Command Line Interface (AWS CLI)
	- Enables you to control multiple AWS services directly from the command line within a tool
	- Available on Windows, macOS, and Linux
	- You can automate actions that services and apps perform through scripts
	- Example: Use commands to launch Amazon EC2 instance, connect an Amazon EC2 instance to a specific Auto Scaling group.
- SDK's
	- Easier to use AWs services through an API designed for your programming language or platform.
	- Enable you to use AWS services with your existing apps or create entirely new apps that will run on AWS
- AWS Elastic Beanstalk
	- Provide code and configuration settings, and Elastic Beanstalk deploys and resources necessary to perform the following tasks:
		- Adjust capacity
		- Load balancing
		- Automatic scaling
		- App health monitoring
- AWS CloudFormation
	- Treat your infrastructure as code. This means you can build an environment by writing lines of code instead of using the AWS Management Console to individually provision resources
	- Provisions your resources in a safe, repeatable manner, enabling you to frequently build your infrastructure and apps without having to perform manual actions
	- Determines the right operations to perform when managing your stack and rolls back changes automatically if it detects errors 


## Module 4: Networking
### Connectivity to AWS
#### Amazon Virtual Private Cloud (Amazon VPC)
- A networking that establishes boundaries around your AWS resources
- Enables you to provision an isolated section of the AWS Cloud.
- In this isolated section, you can launch resources in a virtual network that you define.
- Within a VPC, you can organize your resources into subnets.
- A subnet is a section of a VPC that can contain resources such as EC2 instances

#### Internet Gateway
To allow public traffic from the internet to access your VPC, you attach a **internet gateway** to the VPC
![[Amazon Internet Gateway.png]]
An internet gateway is a connection between a VPC and the internet. Without it no one can access the resources within your VPC

#### Virtual private gateway
To access private resources you use a **virtual private gateway**

Example:
- The internet is a road between your home and the coffee shop
- You are travelling on this road with a bodyguard to protect you
- You are still using the same road as the other customers, but with an extra layer of protection
- The bodyguard is like a virtual private network (VPN) that encrypts your internet traffic from all the other requests around it.
- The virtual private gateway is the component that allows protected internet traffic to enter into the VPC. 
- Even though your connection to the coffee shop has extra protection, traffic jams are possible because you're using the same road as other customers
- A virtual private gateway enables you to establish a VPN connection between your VPC and a private network, such as an on-premises data centre or internal corporate network. 
- A virtual private gateway allows traffic into the VPC only if its coming from an approved network.

![[Virtual Private Gateway.png]]
#### AWS Direct Connect
Is a service that lets you establish a dedicated private connection between your data centre and a VPC

Example:
- There is an apartment building with a hallway directly linking the building to the coffee shop.
- Only the residents of the apartment building can travel through this hallway
- This private hallway provides the same type of dedicated connection as AWS Direct Connect. Residents are able to get into the coffee shop without needing to use the public road shared with other customers.
![[AWS Direct Connect.png]]
Benefits:
- Helps to reduce network costs
- Increase the amount of bandwidth that can travel through your network

### Subnets and Network Access Control Lists
#### Subnets
Is a section of a VPC in which you can group resources based on security or operational needs. Subnets can be public or private
![[Subnets.png]]
**Public Subnets**
- Contain resources that need to be accessible by the public, such as an online store's website
**Private Subnets**
- Contain resources that should be accessible only through your private network, such as database that contains customers' personal info and order histories
In a VPC, subnets can communicate with each other. So an EC2 instance in a public subnet can communicate with databases that are located in a private subnet.

#### Network traffic in a VPC
When a customer requests data from an app hosted in the AWS Cloud, this request is sent as a packet. A packet is a unit of data sent over the internet or a network

It enters into a VPC through an internet gateway. Before a packet can enter into a subnet or exit from a subnet, it checks for permissions. These permissions indicate who sent the packet and how the packet is trying to communicate with the resources in a subnet.

The VPC component that checks packet permissions.

#### Network ACLs (Access Control Lists)
A network ACL is a virtual firewall that controls inbound and outbound traffic at the subnet level. 

Example:
- At an airport, travellers are trying to enter a different country
- Travellers are packets and passport control officers are a network ACL.
- The passport control officer checks travellers' credentials when they are both entering and exiting a country.
- If a traveller is on a approved list, they are able to go through, if not or they are banned, they cannot enter the country

Each AWS account includes a default network ACL. When configuring your VPC, you can use your account's default network ACL or create custom network ACL's

By default, the network ACL's allows all inbound and outbound traffic. This can be modified by adding your own rules. For custom network ACLs, all inbound and outbound traffic is denied until you add rules to specify which traffic to allow. Additionally, all network ACLs have an explicit deny rule. This rule ensures that if packet doesn't match any other rules on the list, the packet is denied.

#### Stateless packet filtering
Network ACLs perform **stateless** packet filtering. They remember nothing and checks packets that cross the subnet border each way; inbound and outbound.

When a packet response for that request comes back to the subnet, the network ACL does not remember your previous request. The network ACL checks the packet response against its list of rules to determine whether to allow or deny.

After a packet enters a subnet, it must have its permissions evaluated for resources within the subnet, such as Amazon EC2 instances.

#### Security Groups
Is a virtual firewall that controls inbound and outbound traffic for an Amazon EC2 instance. Checks packet permissions for an EC2 instance.

By default, a security group denies all inbound traffic and allows all outbound traffic. You can add custom rules to configure which traffic should be allowed; any other traffic would be denied.

Example:
- For an apartment, guests are packets and the door attendant are a security group.
- As guests arrive, the door attendant checks a list to ensure they can enter the building
- However, the door attendant does not check the list again when guests are exiting the building.
If you have multiple EC2 instances within the same VPC, you can associate them with the same security group or use different security groups for each instance.

#### Stateful packet filtering.
Security groups perform **stateful** packet filtering. They remember previous decisions made for incoming packets

Example:
- Sending a request out from an EC2 instance to the internet.
- When a packet response for that request returns to the EC2 instance, the security group remembers your previous request.
- The security group allows the response to proceed, regardless of inbound security group rules.![[Stateful Packet Filtering.png]]

#### Network ACLs & Security Groups
![[Network ACLs & Security Groups.png]]
### Global Networking
#### Domain Name System (DNS)
DNS is the phone book of the internet
DNS resolution is the process of translating a domain name to an IP address.
![[DNS.png]]

#### Amazon Route 53
Is a DNS web service. It gives developers and businesses a reliable way to route end users to internet apps hosted in AWS.

Amazon Router 53 connects user requests to infrastructure running in AWS. It can route users to infrastructure outside of AWS

It can also manage the DNS records for domain names. You can register new domain names directly in Route 53. You can also transfer DNS records for existing domain names managed by other domain registrars. This enables you to manage all of your domain names within a single location. 

#### How Amazon Route 53 and Amazon CloudFront deliver content
![[How Amazon Route 53 and Amazon CloudFront deliver content.png]]
Suppose a Company's app is running on several EC2 instances. These instances are in a Auto Scaling group that attaches to an Application Load Balancer.
1. A customer requests data from the app by going to the company's website
2. Amazon Route 53 uses DNS resolution to identify the company's corresponding IP address. This info is sent back to the customer
3. The customer's request is sent to the nearest edge location through Amazon CloudFront
4. Amazon CloudFront connects to the Application Load Balancer, which sends the incoming packet to an Amazon EC2 instance.
## Module 5: Storage & Databases
### Instance Stores and Amazon Elastic Block Store (Amazon EBS)
#### Instance stores
Provides a temporary block-level storage (acts like a physical hard drive) for an EC2 instance. 
It is disk storage that is physically attached to the host computer for an EC2 instance, and therefor has the same lifespan as the instance.
When the instance is terminated, you lose any data in the instance store.

#### Amazon Elastic Block Store (Amazon EBS)
Is a service that provides block-level storage volumes that you can use with EC2 instances. If you stop or terminate an EC2 instance, all the data on the attached EBS volume remains available. 
To create an EBS volume, you define the configuration (such as volume size and type) and provision it. After you create an EBS volume, it can attach to an EC2 instance.
Because EBS volumes, are for data that needs to persist, it's important to back up the data. You can take incremental backups of EBS volumes by creating EBS snapshots.

#### Amazon EBS Snapshots
Is an incremental backup. This means that the first backup taken of volume copies all the data. For subsequent backups, only the blocks of data that have changed since the most recent snapshot are saved.
Different from full backups in which all the data in a storage volume copies each time a backup occurs.

### Amazon Simple Storage Service (Amazon S3)
#### Object Storage
![[Object Storage.png]]
In object storage, each object consists of data, metadata, and a key.
- **Data**: might be an image, video, text document, or any other type of file.
- **Metadata**: contains information about what the data is, how it is used, the object size, and so on. 
- **Key**: The object's unique identifier.

#### Amazon Simple Storage Service (Amazon S3)
Is a service that provides object-level storage. Amazon S3 stores data as objects in buckets.

You can upload any type of file to S3:
- images
- videos
- media files for a website
- archived documents.

S3 offers unlimited storage space. 
Max file size for an object: 5TB
When uploading a file to S3, you can set permissions to control visibility and access to it. You can also use the S3 versioning feature to track changes to your objects over time. 

#### Amazon S3 storage classes
You pay only for what you use. There is a range of storage classes to select a fit for your business and cost needs. When selecting an Amazon S3 storage class, consider these 2 factors:
- How often you plan to retrieve your data
- How available you need your data to be.

There are 8 categories of S3 storage classes:
- Standard
	- Designed for frequently accessed data
	- Stores data in a minimum of 3 Availability Zones
	- Provides high availability for objects.
	- Good for wide range of use cases, websites, content distribution, and data analytics.
	- S3 has a higher cost than other storage classes intended for infrequently accessed data and archival storage.
- Standard-Infrequent Access (S3 Standard-IA)
	- Ideal for infrequently accessed data but requires high availability when needed
	- Similar to S3 Standard but has a lower storage price and higher retrieval price
	- Store data in a minimum of 3 Availability Zones like Standard.
- One Zone-Infrequent Access (S3 One Zone-IA)
	- Stores data in a single Availability Zone
	- Has a lower storage price than S3 Standard-IA
	- Good for data that can be easily reproduced in the event of an Availability Zone failure
- Intelligent-Tiering
	- Ideal for data with unknown or changing access patterns
	- Requires a small monthly monitoring and automation fee per object
	- Monitors objects' access patterns.
	- If an object isn't accessed for 30 consecutive days, S3 automatically moves it to the infrequent access tier, S3 Standard-IA.
	- If you access an object in the infrequent access tier, S3 automatically moves it to the frequent access tier, S3 Standard
- Glacier Instant Retrieval
	- Works well for archived data that requires immediate access
	- Can retrieve objects within a few milliseconds
- Glacier Flexible Retrieval
	- Low-cost storage designed for data archiving
	- Able to retrieve objects within a few minutes to hours (1 minute to 12 hours)
- Glacier Deep Archive
	- Lowest-cost object storage class ideal for archiving
	- Able to retrieve objects within 12 hours
	- Supports long-term retention and digital preservation for data that might be accessed once or twice a year.
	- Data retrieval from 12-48 hours.
	- All objects from this storage class are replicated and stored across at least 3 geographically dispersed Availability Zones
- Outposts
	- Creates S3 buckets on S3 Outposts
	- Makes it easier to retrieve, store and access data on AWS Outposts.
	- Works well for workloads with local data residency requirements that must satisfy demanding performance needs by keeping data close to on-premises apps.
### Amazon Elastic File System (Amazon EFS)
#### File Storage
In file storage, multiple clients (such as users, apps, servers, and so on) can access data that is stored in shared file folders. 
In this approach, a storage server uses block storage with a local file system to organize files. Clients access data through data file paths.
Compared to block storage and object storage, file storage is ideal for use cases in which a large number of services and resources need to access the same data at the same time.

#### Amazon EFS
- A scalable file system used with AWS cloud services and on-premises resources.
- When you add and remove files, Amazon EFS grows and shrinks automatically.
- It can scale on demand to petabytes without disrupting apps

#### Amazon EBS vs EFS
EBS
- An EBS volume stores data in a single availability zone
- To attach an EC2 instance to an EBS volume, the EC2 instance and EBS volume must reside within the same AZ
EFS
- A regional service. It stores data in and across multiple AZs
- Duplicate storage enables you to access data concurrently from all the AZs in the Region where a file system is located.
- Additionally, on-premises servers can access Amazon EFS using AWS Direct Connect

### Amazon Relational Database Service (Amazon RDS)
#### Relational Databases
- Data is stored in a way that relates it to other pieces of data.
#### Amazon RDS
- A service that enables you to run relational databases in the AWS Cloud
- A managed service that automates tasks such as hardware provisioning, database setup, patching, and backups.
- You can spend less time completing administrative tasks and more time using data to innovate your apps.
- RDS can be integrated with other services to fulfil your business and operational needs, such as using AWS Lambda to query your database from a serverless app.
- Provides a number of different security options. Many RDS database engines offer encryption at rest (protecting data while its stored) and encryption in transit (protecting data while it is being sent and received)

#### Amazon RDS database engines
Available on 6 database engines, which optimize for memory, performance, or IO:
- Amazon Aurora
- PostgreSQL
- MySQL
- MariaDB
- Oracle Database
- Microsoft SQL Server

#### Amazon Aurora
- An enterprise-class relational database
- Compatible with MySQL and PostgreSQL relational databases. 
- Up to 5 times faster than standard MySQL databases and up to 3 times faster than standard PostgreSQL databases.
- Helps to reduce your database costs by reducing unnecessary IO operations, while ensuring that your database resources remain reliable and available
- Consider using it if workloads require high availability
- Replicates 6 copies of your data across 3 AZs 
- Continuously backs up your data to Amazon S3
### Amazon DynamoDB
#### Nonrelational databases
- In nonrelational database, you create tables. A table is a place where you can store and query data.
- These are sometimes referred to as "NoSQL databases" because they use structures other than rows and columns to organize data. 
- One type of structural approach for nonrelational databases is key-value pairs:
	- items (keys)
	- attributes (values)(different features of your data)
- You can add or remove attributes from items in the table at any time. 
- Additionally, not every item in the table has to have the same attribute.
Example:
![[Nonrelational database example.png]]
#### Amazon DynamoDB
- A key-value database service. Delivers single-digit millisecond performance at any scale.
	- **Serverless**: You do not have to provision, patch, or manage servers. Do not have to install, maintain or operate software
	- **Automatic Scaling**: The database shrinks or grows. DynamoDB automatically scales to adjust for changes in capacity while maintaining consistent performance.

### Amazon Redshift
A data warehousing service that you can use for big data analytics. It offers the ability to collect data from many sources and helps you to understand relationships and trends across your data.
### Amazon Database Migration Service
Enables you to migrate relational databases, nonrelational databases, and other types of data stores.
Allows you to move data between a source database and a target database which can be of the same or different types.
During migration, your source database remains operational, reducing downtime for any apps that rely on that database.
Example: Suppose that you have a MySQL database that is stored on-prem in an EC2 instance or RDS. Consider the MySQL database to be your source database. Using AWS DMS, you could migrate your data to a target database, such as an Aurora database.

#### Use Cases for AWS DMS
- **Development and test database migrations**: Enable developers to test apps against production data without affecting production users 
- **Database consolidation**: Combining several databases into a single database
- **Continuous replication**: Sending ongoing copies of your data to other target sources instead of doing a one-time migration

### Additional Database Services
- Amazon Document DB 
	- A document database service that supports MongoDB workloads. (MongoDB is a document database program)
- Amazon Neptune
	- Is a graph database service
	- Use it to build and run applications that work with highly connected datasets, such as recommendation engines, fraud detection, and knowledge graphs.
- Amazon Quantum Ledger Database (Amazon QLDB)
	- Is a ledger database service.
	- To review a complete history of all the changes that have been made to your app data
- Amazon Managed Blockchain
	- Is a service that you can use to create and manage blockchain networks with open-source frameworks
	- Blockchain is a distributed ledger system that lets multiple parties run transactions and share data without a central authority.
- Amazon ElastiCache
	- Is a service that adds caching layers on top of your databases to help improve the read times of common requests
- Amazon DynamoDB Accelerator (DAX)
	- In memory cache for DynamoDB
	- Helps improve response times from single-digit milliseconds to microseconds.

## Module 6: Security
### The AWS shared responsibility model
You treat the environment as a collection of parts that build upon each other.
AWS is responsible for other parts. This concept is known as the shared responsibility model.
The shared responsibility model divides into customer responsibilities (security in the cloud) and AWS responsibilities (security of the cloud).
![[AWS security.png]]
Example:
Homebuilder: Builder (AWS) is responsible for constructing 
Homeowner: (Customer), it is your responsibility to secure everything in the house by ensuring that the doors are closed and locked.

#### Customers: Security in the cloud
- Customers are responsible for the security of everything that they create and put in the AWS Cloud.
- When using AWS services, you, the customer, maintain complete control over your content.
- You are responsible for managing security requirements for your content, including which content you choose to store on AWS, which AWS service you use, and who has access to that content.
- You also control how access rights are granted, managed, and revoked.
- The security steps that you take will depend on factors such as the services as the services that you use, the complexity of your systems, and your company's specific operational and security needs. 
- Steps include selecting, configuring, and patching the operating systems that will run on EC2 instances, configuring security groups, and managing user accounts.

#### AWS: Security of the cloud
- AWS is responsible for security of the cloud. 
- AWS operates, manages, and controls the components at all layers of infrastructure. This includes areas such as the host operating system, the virtualization layer, and even the physical security of the data centres from which services operate.
- AWS is responsible for protecting the global infrastructure that runs all of the services offered in the AWS Cloud. This infrastructure includes AWS Regions, Availability Zones, and edge locations.
- AWS manages the security of the cloud, specifically the physical infrastructure that hosts your resources, which include:
	- Physical security of data centres
	- Hardware and software infrastructure 
	- Network infrastructure
	- Virtualization infrastructure 
- Although you cannot visit AWS data centers to see this protection firsthand, AWS provides several reports from third-party auditors. These auditors have verified its compliance with a variety of computer security standards and regulations.

### User Permissions and Access
#### AWS Identity and Access Management (IAM)
- Enables you to manage AWS services and resources securely.
- IAM gives you the flexibility to configure access based on your company's specific operational and security needs.
- You do this by using a combination of IAM features, which are explored in detail in this lesson:
	- IAM users, groups, and roles
	- IAM policies 
	- Multi-factor authentications
#### AWS account root user
- When you first create an AWS account, you begin with an identity known as the **root user**
- The root is accessed by signing in with the email address and password that you used to create your AWS account. 
- You can think of the root user as being similar to the owner of the coffee shop. It has complete access to all the AWS services and resources in the account. 
![[AWS account root user.png]]
Best Practice:
- Do not use the root user for everyday tasks.
- Instead, use the root user to create your first IAM user and assign it permissions to create other users.
- Create other IAM users, and access those identities for performing regular tasks throughout AWS.
- Only use the root user when you need to perform a limited number of tasks that are only available to the root user.
	- These tasks include:
		- Changing root user email address
		- Changing AWS support plan
#### IAM users
- An identity that you create in AWS. It represents the person or app that interacts with AWS services and resources. It consists of a name and credentials
- By default, a new IAM user in AWS has no permissions associated with it.
- You must grant the IAM necessary permissions such as allowing the user to launch an EC2 instance or create a S3 bucket

Best Practice:
- Create individual IAM users for each person who needs access to AWS
- Allow each IAM user to have a unique set of security credentials which gives additional security
#### IAM policies 
- A document that allows or denies permissions to AWS services and resources
- Enables customization of users' levels of access to resources.
	- Example: Either allow users to access all of the S3 buckets within your AWS account, or only a specific bucket 

Best Practice:
- Follow the security principle of **least privilege** when granting permissions
- This helps prevent users or roles from having more permissions than needed to perform their tasks
#### Example: IAM policy
![[Example IAM Policy.png]]
#### IAM groups
- A collection of IAM users. 
- When an IAM policy is assigned to a group, all users in the group are granted permissions specified by the policy.
#### IAM roles
- An identity that you can assume to gain temporary access to permissions
- Before an IAM user, app or service can assume an IAM role, they must be granted permissions to switch to the role.

Best Practice:
- IAM roles are ideal for situations in which access to services or resources needs to be granted temporarily, instead of long-term

### AWS Organizations
- Use it to consolidate and manage multiple AWS accounts within a central location
- When you create an organization, AWS Organizations automatically creates a root, which is the parent container for all the accounts in your organization 
- You can centrally control permissions for the accounts in your organization using **service control policies (SCPs)** 
- SCPs enable you to place restrictions on the AWS services, resources, and individual API actions that users and roles in each account can access.
- In AWS organizations, SCPs can be applied to the organization root, an individual member account, or an OU, including the AWS account root.

#### Organizational units
- In AWS Organizations, you can group accounts into organizational units (OUs) to make it easier to manage accounts with similar business or security requirements
- When you apply a policy to an OU, all the accounts in the OU automatically inherit the permissions specified in the policy.
- By organizing separate accounts into OUs, you can easily isolate workloads or applications that have specific security requirements
![[Organizational units.png]]

### Compliance
#### AWS Artifact
- A service that provides on-demand access to AWS security and compliance reports and select online agreements.
- Consists of 2 main sections:
	- AWS Artifact Agreements
		- Used by companies to sign an agreement with AWS regarding the the use of certain types of info throughout AWS services
		- You can review, accept, and manage agreements for an individual account and for all your accounts in AWS Organizations.
		- Different types of agreements are offered to address the needs of customers who are subject to specific regulations, such as the Health Insurance Portability and Accountability Act (HIPAA).
	- AWS Artifact Reports
		- Provides compliance reports from third-party auditors.
		- These auditors have tested and verified that AWS is compliant with a variety of global, regional, and industry-specific standards and regulations.
		- Remains up to date with the latest reports released.
		- Can be provided as evidence of AWS security controls.

#### Customer Compliance Centre
- Contains resources to help you learn more about AWS compliance
- You can read customer compliance stories to discover how companies in regulated industries have solved various compliance, governance, and audit challenges.
- You can access compliance whitepapers and documentation on topics such as:
	- AWS answers to key compliance questions
	- An overview of AWS risk and compliance
	- An auditing security checklist
- Also includes an auditor learning path. Designed for individuals in auditing, compliance, and legal roles who want to learn more about how their internal operations can demonstrate compliance using the AWS Cloud.

### Denial-of-Service Attacks
#### AWS WAF
- Web Application Firewall
#### AWS Shield
- Is a service that protects applications against DDoS attacks.
- Provides 2 levels of protection:
	- Standard
		- Automatically protects all customers at no cost.
		- Protects resources from the most common, frequently occurring types of DDoS attacks
		- As network traffic comes into your applications, AWS Shield Standard uses a variety of analysis techniques to detect malicious traffic in real time and automatically mitigates it.
	- Advanced
		- A paid service that provides detailed attack diagnostics and the ability to detect and mitigate sophisticated DDoS attacks. 
		- Also integrates with other services, such as Amazon CloudFront, Amazon Route 53, and Elastic Load Balancing.
		- Can be integrated with AWS WAF by writing custom rules to mitigate compl




### Additional Security Services
#### AWS Key Management Service (AWS KMS)
- Enables you to perform encryption operations through the use of **cryptographic keys**(a random string of digits used for encrypting and decrypting data)
- Used to create, manage, and use cryptographic keys.
- Also control the use of keys across a wide range of services and in your apps
- Choose the specific levels of access control that you need for your keys
#### AWS WAF
- A web application firewall that lets you monitor network requests that come into your web apps
- Works together with CloudFront and an Application Load Balancer
- Works similarly too the network access control lists, however it does it by using **web access control list (ACL)** to protect your AWS resources.
- Prevents malicious requests from blocked IP addresses
#### Amazon Inspector
- Perform automated security assessments
- Helps to improve the security and compliance of apps by running automated security assessments.
- Checks apps for security vulnerabilities and deviations from security best practices, such as open access to EC2 instances and installations of vulnerable software versions.
- After assessment, provides a list of security findings. This list prioritizes by severity level, including a detailed description of each security issue and a recommendations for how to fix it.
- However, AWS does not guarantee that following the provided recommendations resolves every potential security issue.

#### Amazon GuardDuty
- A service that provides intelligent threat detection for your AWS infrastucture and resources. 
- It identifies threats by continuously monitoring the network activity and account behavior within your AWS environment.
- If threats are detected, you can review detailed findings about them from the AWS management console. These include:
	- Recommended steps for remediation.
	- You can configure AWS Lambda functions to take remediation steps automatically in response to the security findings.

## Module 7: Monitoring and Analytics
### Amazon Cloud Watch
- A web service that enables you to monitor and manage various metrics and configure alarm actions based on data from those metrics.
- Uses metrics to represent the data points for your resources.
- AWS services send metrics to CloudWatch, then CloudWatch uses these metrics to create graphs automatically that show how performance has changed over time

#### CloudWatch alarms
- You can create alarms that automatically perform actions if the value of your metric has gone above or below a predefined threshold.
- Example:
	- Create a CloudWatch alarm that automatically stops an EC2 instance when the CPU utilization percentage has remained below a certain threshold for a specified period to save money

### AWS CloudTrail
- Records API calls for your account.
- The recorded information includes these details of the API caller:
	- identity
	- source IP address
	- time
	- etc
- Think of it as a trail or log of actions
- Able to view a complete history of user activity and API calls for your applications and resources.
- Typically updated in CloudTrail within 15 minutes after an API call.
- Able to filter events by specifying the time and date that an API call occurred, the user who requested the action, the type of resource that was involved in the API call, and more.

Example of a log:
On January 1, 2020 at 9:00 AM, IAM user John created a new IAM user (Mary) through the AWS Management Console.

#### CloudTrail Insights
- Allows CloudTrail to automatically detect unusual API activities in your AWS account.
- Example: CloudTrail Insights might detect that a higher number of EC2 instances than usual have recently launched in your account

### AWS Trusted Advisor
- A web service that inspects your AWS environment and provides real-time recommendations in accordance with AWS best practices.
- Compares its findings to AWS best practices in 5 categories:
	- Cost optimization
	- Performance
	- Security
	- Fault tolerance
	- Service limits
- It then provides a lists of recommended actions and additional resources to learn more about AWS best practices

#### AWS Trusted Advisor Dashboard
![[AWS Trsuted Advisor Dashboard.png]]
There are 3 categories of checks:
- Green Checkmark: Indicates number of items for which it detected **no problems**
- Orange Triangle: Number of recommended **investigations**
- Red Circle: Number of recommended **actions**

## Module 8: Pricing & Support
### AWS Free Tier
- 3 types of offers:
	- Always Free
		- These offers do not expire and are available to all AWS customers
		- For example, AWS Lambda allows 1 million free requests and up to 3.2 million seconds of compute time per month. Amazon DynamoDB allows 25 GB of free storage per month.
	- 12 Months Free
		- These offers are free for 12 months following your initial sign-up date to AWS
		- Examples include specific amounts of Amazon S3 Standard Storage, thresholds for monthly hours of Amazon EC2 compute time, and amounts of Amazon CloudFront data transfer out.
	- Trials
		- Short-term free trial offers start from the date you activate a particular service. The length of each trial might vary by number of days or the amount of usage in the service.
		- For example, Amazon Inspector offers a 90-day free trial. Amazon Lightsail (a service that enables you to run virtual private servers) offers 750 free hours of usage over a 30-day period.

### AWS Pricing Concepts
- 3 Categories of pay-as-you-go
	- Pay for what you use
		- For each service, you pay for exactly the amount of resources that you actually use, without requiring long-term contracts or complex licensing
	- Pay less when you reserve
		- Some services offer reservation options that provide significant discount compared to On-Demand Instance pricing
		- Example: EC2 instance savings plan, which allows you to save up to 72% over the equivalent On-Demand Instance capacity
	- Pay less with volume-based discounts when you use more.
		- Some services offer tiered pricing, so the per-unit cost is incrementally lower with increased usage.
		- Example: S3 storage, the more space you use, the less you pay per GB
#### AWS Pricing Calculator
- Lets you explore AWS services and create an estimate for the cost of your use cases on AWS. 
- You can organize your AWS estimates by groups that you define.
- A group can reflect how your company is organized, such as providing estimates by cost center.
- When you have created an estimate, you can save it and generate a link to share it with others.
- Example: For EC2, if your not sure of the Region and instance type you might need, you can enter details such as the OS, memory requirements, and IO requirements and the calculator will show an estimated comparison of different option

#### AWS pricing examples
**AWS Lambda**
- You are charged based on the number of requests for your functions and the time it takes for them to run.
- Allows 1 million free requests and up to 3.2 million seconds of compute time per month.
- Save costs using a **Compute Savings Plans** which offers lower compute costs in exchange for committing to a consistent amount of usage over a 1 or 3 year term.
Example:
![[AWS Lambda Pricing Example.png]]
**Amazon EC2**
- Pay for only the compute time that you use while your instances are running.
- **Spot Instances** would save up to 90% of the costs for workloads that are able to withstand interruptions
- Other plans are Savings Plans and Reserved Instances 
Example:
![[Amazon EC2 Pricing Example.png]]
**Amazon S3**
There a few cost components:
- **Storage**: 
	- You pay for only the storage that you use. 
	- You are charged the rate to store objects in your Amazon S3 buckets based on your objects’ sizes, storage classes, and how long you have stored each object during the month.
- **Requests and data retrievals**: 
	- You pay for requests made to your Amazon S3 objects and buckets. For example, suppose that you are storing photo files in Amazon S3 buckets and hosting them on a website. 
	- Every time a visitor requests the website that includes these photo files, this counts towards requests you must pay for.
- **Data transfer**: 
	- There is no cost to transfer data between different Amazon S3 buckets or from Amazon S3 to other services within the same AWS Region. 
	- However, you pay for data that you transfer into and out of Amazon S3, with a few **exceptions:**
		- There is no cost for data transferred into Amazon S3 from the internet or out to Amazon CloudFront.
		- There is also no cost for data transferred out to an Amazon EC2 instance in the same AWS Region as the Amazon S3 bucket.
- **Management and replication**
	- You pay for the storage management features that you have enabled on you account's Amazon S3 buckets
	- These features include S3 inventory, analytics, and object tagging.

### Billing Dashboard
- The **AWS Billing & Cost Management Dashboard** to pay your AWS bill, monitor your usage, and analyse and control your costs.
	- Compare your current month-to-date balance with the previous month, and get a forecast of the next month based on current usage.
	-  View month-to-date spend by service.
	- View Free Tier usage by service
	- Access Cost Explorer and create budgets
	- Purchase and manage Savings Plans
	- Publish AWS Cost and Usage Reports

### Consolidated Billing
- Consolidated Billing is provided by AWS Organizations
- Enables you to receive a single bill for all AWS accounts in your organization
- Easily track the combined costs of all the linked accounts in your organization.
- The default maximum number of accounts allowed for an organization is 4
	- This can be increased through AWS Support
- On a monthly bill, you can, review itemized charges incurred by each account. This enables you to have greater transparency into your organization's accounts while still maintaining the convenience of receiving a single monthly bill.
- Another benefit of consolidated billing is the ability to share bulk discount pricing, Savings Plans, and Reserved Instances across the accounts in your organization.
- For instance, one account might not have enough monthly usage to qualify for discount pricing. However, when multiple accounts are combined, their aggregated usage may result in a benefit that applies across all accounts in the organization.

### AWS Budgets
- Create budgets to plan your service usage, service costs, and instance reservations
- The info in AWS Budgets updates 3 times a day. This helps to accurately determine how close your usage is to your budgeted amounts or to the AWS Free Tier limits.
- You can also set custom alerts when your usage exceeds the budgeted amount.
#### Example: AWS Budgets
![[AWS Budgets Example.png]]
### AWS Cost Explorer
- Tool that lets you visualize, understand, and manage your AWS costs and usage over time
- Includes a default report of the costs and usage for your top 5 cost-accruing AWS services.
- You can apply custom filters and groups to analyse your data
![[Pasted image 20250612124331.png]]
### AWS Support Plans
#### AWS Support
- Offers 4 different support plans to help troubleshoot issues, lower costs, and efficiently use AWS services
	- Basic
	- Developer
	- Business
	- Enterprise On-Ramp
	- Enterprise
#### Basic
- Free for all AWS customers
- Includes access to whitepapers, documentation, and support communities.
- Able to contact AWS for billing questions and service limit increases.
- Access to a limited selection of AWS Trusted Advisor checks
- Able to use **AWs Personal Health Dashboard** which provides alerts and remediation guidance when AWS is experiencing events that may affect you.

#### Developer
- Lowest cost
- Access to:
	- Best practice guidance
	- Client-side diagnostic tools
	- Building-block architecture support, which consists of guidance for how to use AWS offerings, features, and services together

#### Business Support
- Mid cost
- Access to:
	- Use-case guidance to identify AWS offerings, features, and services that can best support your specific needs
	- All AWS Trusted Advisor Checks
	- Limited support for 3rd party, such as common OS and app stack components

#### Enterprise On-Ramp Support
- Mid cost
- Access to:
	- A pool of Technical Account Managers to provide proactive guidance and coordinate access to programs and AWS experts
	- A Cost Optimization workshop (once a year)
	- A Concierge Support Team for billing and account assistance
	- Tools to monitor costs and performance through Trusted Advisor and Health API/Dashboard
- The proactive guidance given by Technical Account Managers:
	- Consultative review and architecture guidance (one per year)
	- **Infrastructure Event Management** support (one per year)
	- Support automation workflows
	- 30 minutes or less response time for business-critical issues

#### Enterprise Support
- High Cost
- Access to:
	- A designated Technical Account Manager to provide proactive guidance and coordinate access to programs and AWS experts
	- Concierge support team for billing and account assistance
	- Operations Reviews and tools to monitor health
	- Training and Game Days to drive innovation
	- Tools to monitor costs and performance through Trusted Advisor and Health API/Dashboard
- The proactive guidance given by Technical Account Managers:
	- Consultative review and architecture guidance
	- **Infrastructure Event Management** support
	- Cost Optimization Workshop and tools
	- Support automation workflow
	- 15 minutes or less response time for business-critical issues

#### Technical Account Manager (TAM)
- Primary point of contact at AWS
- Educates, empowers and evolves your cloud journey across the full range of AWS services
- Provides expert engineering guidance, help you design solutions that effectively integrate AWS services
- Assist with cost-effective and resilient architectures
- Provides direct access to AWS programs and a broad community of experts.

### AWS Marketplace
- A digital catalog that includes thousands of software listings from independent software vendors
- Use it to find, test, and buy software that runs on AWS
- Able to access:
	- Pricing options
	- Available support
	- Reviews
- Explore software solutions by industry and use case
- Categories:
	- Infrastructure Software
	- DevOps
	- Data Products
	- Professional Services
	- Business Applications
	- Machine Learning
	- Industries
	- IoT

## Module 9: Migration & Innovation
### AWS Cloud Adoption Framework (AWS CAF)
- The AWS CAF organizes guidance into 6 areas of focus, called **Perspectives**
- Each Perspective addresses distinct responsibilities
- The planning process helps the right people across the organization prepare for the changes ahead.
- In general, **Business,People and Governance** focus on **Business** capabilities, whereas the **Platform, Security and Operations** focus on technical capabilities
#### Business Perspective
- Ensures that IT aligns with business needs and that IT investments link to key business results
- Used to create a strong business case for cloud adoption and prioritize cloud adoption initiatives.
- Ensure business strategies and goals align with your IT strategies and goals
- Common roles:
	- Business Managers
	- Finance Managers
	- Budget Owners
	- Strategy Stakeholders

#### People Perspective
- Supports development of an organization-wide change management strategy for successful cloud adoption
- Used to evaluate organizational structures and roles, new skill and process requirements, and identity gaps.
- Helps prioritize training, staffing, and organizational changes.
- Common roles:
	- Human resources
	- Staffing
	- People managers

#### Governance Perspective
- Focuses on the skills and processes to align IT strategy with business strategy
- Ensures that you maximize the business value and minimize risks
- Understand how to update staff skills and processes necessary to ensure business governance in the cloud
- Manage and measure cloud investments to evaluate business outcomes.
- Common roles:
	- Chief Information Officer (CIO)
	- Program managers
	- Enterprise architects
	- Business analysts
	- Portfolio managers

#### Platform Perspective
- Includes principles and patterns for implementing new solutions on the cloud, and migrating on-premises workloads to the cloud
- Use a variety of architectural models to understand and communicate the structure of IT systems and their relationships 
- Describe the architecture of the target state environment in details
- Common roles:
	- Chief Technology Officer (CTO)
	- IT managers
	- Solutions architects

#### Security Perspective
- Ensures that the organization meets security objectives for visibility, auditability, control, and agility
- Use the AWS CAF to structure the selection and implementation of security controls that meet the organization's needs.
- Common roles:
	- Chief Information Security Officer (CISO)
	- IT security managers
	- IT security analysts
#### Operations Perspective
- Helps enable, run, use , operate, and recover IT workloads to the level agreed upon with your business stakeholders.
- Define how day-to-day, quarter-to-quarter, and year-to-year business is conducted
- Align with and support the operations of the business
- AWS CAF helps these stakeholders define current operating procedures and identify the process changes and training needed to implement successful cloud adoption
- Common roles:
	- IT operations managers
	- IT support managers

### Migration Strategies
#### 6 Strategies for Migration
**Rehosting**
- Known as "lift-and-shift" involves moving apps without changes. 
**Replatforming**
- Known as "lift, tinker, and shift" involves making a few cloud optimizations to realize a tangible benefit.
- Optimization is achieved without changing the core architecture of the app
**Refactoring/re-architecting**
- Involves reimagining how an app is architected and developed by using cloud-native features. 
- Driven by a strong business need to add features, scale, or performance that would otherwise be difficult to achieve in the app's existing environment
**Repurchasing**
- Involves moving from a traditional license to a software-as-a-service model
- Example: a business might choose to implement the repurchasing strategy by migrating from a customer relationship management (CRM) system to Salesforce.com.
**Retaining**
- Consists of keeping apps that are critical for the business in the source environment.
- This might include applications that require major refactoring before they can be migrated, or, work that can be postponed until a later time.
**Retiring**
- The process of removing apps that are no longer needed.
### AWS Snow Family
#### AWS Snow Family members
- AWS Snow Family is a collection of physical devices that help to physically transport up to exabytes of data into and out of AWS
- Composed of **AWS Snowcone, AWS Snowball and AWS Snowmobile**
- These devices offer different capacity points, and most include built-in computing capabilities. 
- AWS owns and manages the Snow Family devices and integrates with AWS security, monitoring, storage management, and computing capabilities

#### AWS Snowcone
- Small, rugged, and secure edge computing and data transfer device
- Features:
	- 2 CPUs
	- 4 GB memory
	- up to 14 TB of usable storage
#### AWS Snowball
- **Snowball Edge Storage Optimized**
	- Well suited for large-scale data migrations and recurring transfer workflows, in addition to local computing with higher capacity needs
	- Storage: 80 TB of HDD for block volumes and S3 compatible object storage and 1 TB of SATA SSD for block volumes
	- Compute: 40 vCPUS and 80 GiB of memory to support EC2 sbe1 instances (equivalent to C5)
- **Snowball Edge Compute Optimized**
	- Provides powerful computing resources for use cases such as machine learning, full motion video analysis, analytics, and local computing stacks
	- Storage: 80 TB usable HDD capacity for S3 compatible object storage or EBS compatible block volumes and 28 TB of usable NVMe SSD capacity for Amazon EBS compatible block volumes.
	- Compute:104 vCPUs, 416 GiB of memory, and an optional NVIDIA Tesla V100 GPU. Devices run Amazon EC2 sbe-c and sbe-g instances, which are equivalent to C5, M5a, G3, and P3 instances.

#### AWS Snowmobile
- An exabyte-scale data transfer service used to move large amounts of data to AWS
- You can transfer up to 100 petabytes of data per snowmobile, a 45-foot long ruggedized shipping container, pulled by a semi trailer truck.
### Innovation with AWS
#### AWS SageMaker
- Quick and easy begin working on ML projects
#### AWS Lex
- Create conversational interfaces
#### Amazon Textract
- ML service that automatically extracts text and data scanned from documents
#### Amazon Augmented AI
- Builds workflows that are required for human review of ML predictions
## Module 10: AWS WAF
- Provides a way for you to consistently measure your architecture against best practices and design principles and identify areas for improvement
- The 6 pillars are:
	- Operational Excellence
		-  ability to run and monitor systems to deliver business value and to continually improve supporting processes and procedures.
	- Security
	- Reliability
		- Ability to
			-  Recover from infrastructure or service disruptions
			- Dynamically acquire computing resources to meet demand
			- Mitigate disruptions such as misconfigurations or transient network issues
		- ncludes testing recovery procedures, scaling horizontally to increase aggregate system availability, and automatically recovering from failure.
	- Performance Efficiency
		- ability to use computing resources efficiently to meet system requirements and to maintain that efficiency as demand changes and technologies evolve.
		- Evaluating the performance efficiency of your architecture includes experimenting more often, using serverless architectures, and designing systems to be able to go global in minutes.
	- Cost Optimization 
		- ability to run systems to deliver business value at the lowest price point.
		- Cost optimization includes adopting a consumption model, analyzing and attributing expenditure, and using managed services to reduce the cost of ownership.
	- Sustainability




























References








