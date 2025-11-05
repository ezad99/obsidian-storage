2024-06-22 08:34

Status: #new 

Tags: [[ECS]]

# ECS Tasks & Scheduling
A Task is the instantiation of a task definition within a cluster

After creating a task definition for your app, you can specify the number of tasks that will run on your cluster

Each task that uses Fargate launch type has its own isolation boundary and does not share the underlying kernel, CPU resources, memory resources or elastic network interface with another task

The ECS Task Scheduler is responsible for placing tasks within your cluster
	There are several scheduling options 
	e.g. you can define a service that runs and maintains a specified number of tasks simultaneously

# References

