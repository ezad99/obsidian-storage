2024-06-22 08:39

Status: #new 

Tags: [[ECS]]

# ECS Services
ECS Service runs and maintains a specified number of instances of a task definition simultaneously in an ECS Cluster

If any of the tasks fail or stop for any reason, the ECS service scheduler launches another instance of the task definition to replace it and maintain the desired number of tasks

Also able to optionally run the service behind a load balancer
	The load balancer distributes traffic across the tasks that are associated with the service

Service Scheduler Strategies
	Replica
		Places and maintains the desired number of tasks across your cluster
		By default, the service scheduler spreads tasks across Availability Zones
		You can use task placement strategies and constraints to customize task placement decisions
	Daemon
		Deploys Exactly 1 task on each active container instance that meets all of the task placement constraints that you specify in your cluster
		The service scheduler evaluates the task placement constraints for running tasks and will stop tasks that do not meet the placement constraints.
		When using Daemon, there is no need to specify a desired number of tasks, a task placement strategy, or use Service Auto Scaling policies

# References

