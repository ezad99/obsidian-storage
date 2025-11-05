2024-06-20 17:45

Status: #new

Tags: [[ECS]],[[EC2]],[[Lambda]]

# EC2 vs ECS vs Lambda
All are different compute(hosting locations) for our app

EC2 (Elastic Cloud Compute)
	Has Flexible Instances/Virtual Machines
		These can scale up or down depending on the demand
			e.g. Memory/Storage/Computation demands
	You can do what ever you want
		Such as install databases or hosts websites
	Security is a concern in EC2

ECS (Elastic Container Store)
	Docker ecosystem
	Uses Clusters & Tasks
		Clusters are a set of EC2 machines
			Treat the EC2 machines as an abstract resource to be used by tasks
		Tasks use the clusters
			Can be long or short term
	Deploy images to an ECR (Elastic Container Repository)
		Images are attached to Tasks
			Tasks are deployed into Clusters
				Clusters can be either EC2 or Fargate based
					Load balancers can be attached to make it more robust

Lambda (Operate at Function Level)
	Abstracts complexity from EC2 & ECS
		Sacrifices Control
	Works on the unit of code
	Upload file to lambda
		Give it an entry point
			An ID is given back
				The ID will be used to run the code


# References
[# AWS EC2 vs ECS vs Lambda | Which is right for YOU?](https://www.youtube.com/watch?v=-L6g9J9_zB8)
