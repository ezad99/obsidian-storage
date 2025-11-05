2024-10-01 07:54

Status: #new 

Tags: [[Artificial Intelligence]]

# AI Foundations

**Agents-Centric view of AI**
	What is an Agent?
		Anything that can be viewed as 
			Perceiving its environment through sensors
			Acting upon that environment through actuators (humans, robots, chatbots, thermostats)
	![[Pasted image 20241001080052.png]]
	Agent Function
		Maps from prior/build-in knowledge π, and percepts P, to actions A
		![[Pasted image 20241001081125.png]]
		Percepts, P
			The sensory input an AI Agent receives from its environment 
			Perceptual inputs, percepts and sequence/history as reported by the sensors
		Actuators & Actions, A
			What ever ways the agent has to influence the environment via its actuators (visual, physical, audio, computer commands)
		Prior Knowledge, π
			Any hard coded constraints or knowledge about the environment 
				e.g. If temp < 40, not good
		Function, f
			An external characterization of the agent
			Implemented as a agent program and runs on a physical device
	PEAS Model
		Useful to 'think' about any AI task as a PEAS model
			**P**erformance measure
				Defines "good behaviour" in a specific context
			**E**nvironment
				A specification of the physical (or virtual) environment the agent is expected to operate in.
			**A**ctuators
				The types and physical properties of the actuators available to the agent. 
				Limits what the agent can do
			**S**ensors:
				The types and physical properties of the sensors available to the agent
				Limits what the agent can know about the environment
		PEAS view of existing AI Models
			Maze Finding
			![[Pasted image 20241001084421.png]]
				P: Minimize steps taken or time spent in maze
				E: Size of the maze, start, goal, paths and obstacles
				A: Movement through a grid, physically or virtually
				S: Reacting to obstacle, physically or virtually
			ChatGPT
				P: Maximize - correctness, relevance or Minimize - reading effort, misinformation
				E: Virtual space of all possible answers (quantized in terms of tokens)
				A: Generating a token conditioned on the input and what's generated before
				S: The API interface that gets a user's text
			Self-Driving Cars
				P: Maximize - safety or Minimize - time to destination (P can be conflicting to each other)
				E: The surface on which the car is driven, the obstacles, road corners
				A: Brake, accelerator, gear
				S: Sequences of images captured, or physical sensors such as wetness of road 

**Rationality of Agents**
	What is rational behaviour?, What does it mean to do a thing 'the right way'?
		Consider the consequences (the P) of an agents behaviour
		For each possible percept (sequence), P
		a **rational agent** selects an action (sequence)
		which is expected to maximize its performance measure given the evidence provided by the percept (sequence) so far and whatever prior knowledge the agent has
	Rationality in the vacuum world
		Scenario: You want to clean rooms with a vacuum efficiently without wasting your battery
		EAS of the task
			E: 2 rooms (no prior knowledge of the dirt distribution)
			A: Left, Right, Suck
			S: Correctly identify room is clean
		Which P Leads to rationality
			1. +1 for sucking up a portion of dirt
			2. +1 for each clear square observed
			3.  +1 for each clear square; -0.1 for taking an action due to battery usage
		Correct answer is number 3, as it takes into account the battery usage
		Rule of Thumb
			Choose a P on the basis of
				Objective view-point: What is required in the environment
				Subjective view-point: NOT on how an agent should behave
			What IS Rationality and what it IS NOT
				IS NOT omniscient
					An agent can't know the precise outcome of the action in the environment.
					It can only estimate the outcome based on previous percepts
				DOES NOT imply success
					Being rational does not imply success in solving the task
				CAN LEAD to exploration, learning and autonomy

**Environment Types**
	Fully VS Partially observable
		Fully
			Access to all relevant info via the sensors
		Partially
			If an agent acts based on noisy or broken sensors
			Or sensors simply do not capture the relevant info
	Deterministic VS Stochastic
		Deterministic
			The next state of the environment is fully captured by current state and the action to be carried out
		Stochastic
			Can not determine the next state based on the current state and action due to randomness in the environment
	Static VS Dynamic
		Static
			Environment never changes
		Dynamic
			Environment changes while we decide what to do, time matters
				e.g.
					Ice melts at a certain rate on a frozen lake environment
					Dirt accumulates with certain probability in the vacuum environment
		Semi-Static
			World is the same, but the performance score changes
				e.g.
					Performance measure changed to maximizing battery life as opposed to just the room cleanliness in the vacuum environment
	Discrete VS Continuous
		Discrete
			State of the environment are determined among a set of discrete possibilities 
				e.g. Chess
			Discrete Actions
				e.g. Move left or right
			Discrete Percepts
				e.g. Dirty, not dirty
		Continuous
			World has infinitely many states 
				e.g. temperature
			Actions are continuous
			Percepts are continuous
				e.g. human vision
	Episodic VS Sequential
		Episodic
			Single actions based on current percept only
				e.g. Cleaning Robot in a Grid World
		Sequential
			Current action influences all future decision
				e.g. Chess, Maze Finder

**Agent Types**
	Tabular (Rule-Based) Agents
	![[Pasted image 20241001155229.png]]
		A Pre-configured look-up table of state transitions
		Keeps the entire percept sequence in memory
		Feasible to define for a small-scaled task such as vacuuming 2 rooms
	Reflex-based Agents
	![[Pasted image 20241001160339.png]]
		Action is NOT a function of historical percepts but depends ONLY on the current percept (state)
		Does not keep track of how the environment changes with an action
			e.g. Sucking dirt may introduce a new state where a room is neither completely clean nor dirty
	Model-based Agents
	![[Pasted image 20241001160644.png]]
		Learns mappings between the actions and consequences
	Goal-based Agents
	![[Pasted image 20241001162720.png]]
		For some problems, the goal state is known
			The 2 goal states in vacuum world
				2 clean rooms with the agent in any one of the rooms
		Need an evaluation function over states that are 'closer' to the goal state 
		Limitations
			Can't handle
				Multiple goals
				Conflicting goals
				Ill-specified goals
		Move towards the goal that's 'closer' from the current state
	Utility-based Agents
	![[Pasted image 20241001205351.png]]
	Requires a trade-off
		A little bit of dirt in the other room with enough battery is better than a fully dead battery and 2 clean rooms
		A rational agent should perform actions that results in states that maximize utility
			For the vacuum world, it might be:
			u(state) = 0.9 x cleanliness + 0.1 x charge
	General Learning Agent
	![[Pasted image 20241002092557.png]]
		Performance Element
			Selects actions - similar to a static agent as we have seen so far.
		Learning Element
			Find improvements
		Critic Element
			Feedback from the environment which affects Learning Element
		Problem Generator
			Choose sub-optimal paths to explore more about the environment to discover better actions in the long run
		Example
			Ice Field
			![[Pasted image 20241002115210.png]]
			Performance Element
				Utility function that minimizes the risk of falling down into a hole and maximizes the chance of getting the reward. 
			Learning Element
				Discover that 2 adjacent holes are more risky than a single one
			Critic Element
				Gives a high negative reward when an agent actually falls into a hole
			Problem Generator
				The agent needs to fall into holes (some risk taking ability) to improve its learning of manoeuvring techniques around holes






























# References

