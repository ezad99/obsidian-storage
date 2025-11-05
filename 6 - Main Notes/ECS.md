2024-06-21 10:12

Status: 

Tags: [[SRE (Site Reliability Engineering)]],[[Containers]],[[EC2]]

# ECS
ECS is a Managed Container Orchestrator
	Same family as Docker Swarm & Kubernetes

What does an Orchestrator do?
	It's the brains of everything
	It manages the lifecycle of a container
		Creates one when needed
		Deletes one when no longer needed
		Restarts one if it crashes
	Deploys & load-balances the app across multiple servers
		So it does not rely on only one server which could cause a single point of failure
	Autoscaling to handle change in traffic
		Scale up if traffic increases
		Scale down if traffic decreases
	Rolling out changes without affecting users

ECS vs Others
	[[Docker vs ECS| Docker alone is too simple]]
	Other Orchestrators such as Kubernetes are too complex
	ECS is the right balance

ECS Launch Types
	EC2
	Fargate

ECS is the brains, but does not actually have any servers
	It only manages them
	Still needs the infrastructure to run the containers on
	It requires a Cluster 
		Which is a bunch of resources/EC2 machines
	ECS just allocates those containers on the cluster

EC2 Launch
	We still have to manage the EC2 instances
	![[Pasted image 20240621104051.png]]
		1. We need to install Docker to run the containers
		2. Install ECS Agent so ECS control plane can communicate with it
		3. Install Firewall for security
		4. Routine Patches & Updates so everything's up to date
	ECS only manages the containers
	With this we have full control over the infrastructure

ECS Fargate
	AWS manages the infrastructure
	![[Pasted image 20240621115508.png]]
	Fargate follows a serverless architecture
	When we send an app to ECS
		ECS sees we have no servers to run our app
		ECS talks to Fargate and Fargate creates servers on demand
	We don't need to maintain EC2 servers
	We only pay for what we use

ECS Task Definition
	![[Pasted image 20240621120027.png]]
	User we dockerise app and create a Docker file
	The file is sent to Docker Hub
	Then you define a Task Definition file on ECS
		A Task Definition File is a blueprint that describes how containers should launch
			It has CPU/Memory
			What images/ports/volumes should be used
			Basically has all the configurations in a docker-compose.yml file
			![[Pasted image 20240621115943.png]]

ECS Tasks
	![[Pasted image 20240621120732.png]]
	An instance of a Task Definition
		If we wanted 2 instances, we would have 2 tasks
	Basically a running container(s) with settings defined in the Task Definition

ECS Service
	Ensures a certain number of tasks are running at all times
	Restarts containers that have exited/crashed
	If EC2 instance fails, the service will restart the task on a EC2 instance that still works on the cluster

Load Balancers
	Routes External Traffic to your service
	Make sure traffic is evenly handled
	If we add new instance, the load balancer will dynamically allocate to it evenly
# References
[[Docker vs ECS]]
