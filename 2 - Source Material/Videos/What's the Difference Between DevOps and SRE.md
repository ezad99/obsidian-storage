2024-06-18 13:05
# Reference
[# What's the Difference Between DevOps and SRE? (class SRE implements DevOps)](https://www.youtube.com/watch?v=uTEL8Ff1Zvk&list=PLIivdWyY5sqJrKl7D2u-gmis8h9K66qoj)

# Notes
Developers - agility
Operations - stability

Developers wanted to move faster for development while operations wanted to move slower for stability

DevOps is used to break the barrier between Developers and Operations

DevOps can be reduced into 5 key areas 
	Reduce Organization Silos
		Breakdown barriers between teams
	Accept Failure as Normal
		Computers and humans are unreliable
	Implement  Gradual Change
		Small incremental changes are easier to review and simple to rollback
	Leverage tooling & automation
	Measure everything

We can think of SRE as a class that implements the super class DevOps
``` 
class SRE implements DevOps
```

Reduce Organization Silos = Share Ownership with developers, use same tooling so everything has the same view when working with production

Accept Failure as Normal = Blameless Post Mortems and SLO

Implement Gradual Change = Reduce costs of failure

Leverage Tooling & Automation = Automate this year's job away

Measure everything = Measure Toil and Everything