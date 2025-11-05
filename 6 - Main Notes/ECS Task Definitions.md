2024-06-22 08:26

Status: #new 

Tags: [[ECS]]

# ECS Task Definitions
To prepare your app to run Amazon ECS, you create a Task Definition

Task Definition is a test file in JSON 
	It describes one or more containers, up to 10, that form your app

It is basically a blueprint for your app

Task definition has various parameters 
	e.g.
		Containers
		Launch Type
		Ports
		Data Volumes
	Specific parameters depend on the Launch Type

Example:
	Task Definition containing a single container that runs an NGINX web server, using Fargate Launch Type

```
{
	"family":"webserver",
	"containerDefinitions": [
		{
			"name":"web",
			"image":"nginx",
			"memory":"100",
			"cpu":"90"
		}
	]
	"requiresCompatibilities":[
	"FARGATE"
	],
	"networkMode": "awsvpc", 
	"memory": "512", 
	"cpu": "256"
}
```

# References

