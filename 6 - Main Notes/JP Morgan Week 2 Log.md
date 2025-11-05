2025-09-24 07:31

Status: #new 

Tags:  [[JP Morgan]], [[Log]]

# JP Morgan Week 2 Log
### Monday (22/09/25)
My Behavioural Style: Peacekeeper

Stages of team:
- Forming
- Storming
- Norming
- Performing
- Mourning

Shortcuts for projects:
To open a project: ds p o
- p: project 
- o: open

To sync a project: ds p s
- s: sync

3-layer-architecure
1. Presentation Layer (Frontend/API Layer)
	- Handles user interaction and incoming /outgoing requests
	- Components:
		- Frontend (UI): React, Angular
		- Controllers (Backend side): Entry points for HTTP requests
	- Example:
		- Users clicks "Get Profile": Browser sends "GET/users/1"
		- Controller method catches this request
2. Application Layer (Middle Layer/ Business Layer) 
	- Contains the business logic (Any kind of filtering, calculation, checking and processing)
	- Components:
		- Services: Apply business rules, orchestrate repositories/mappers
		- Mappers: Convert entities <-> DTOs so that the database layer and API layer stay decoupled.
	- Example:
		- Service ask repository for "User" entity.
		- Service applies rules (e.g., check if user is active)
		- Mapper converts entity -> DTO
3. Data layer (Persistence Layer)
	- Purpose: Manages storage and retrieval of data
	- Components:
		- Repositories: Interact with the database (via SQL or ORM)
		- Database: PostgreSQL, MySQL, MongoDB
	- Example:
		- Repository runs `SELECT * FROM users WHERE id = 1`.
		- Returns a `User` entity to the service.

### Tuesday (23/09/25)
Inversion of control
- Definition: Your code controls object creation
- With IoC, you invert the the control - instead of your code creating and managing objects, the Spring container (IoC container) does it for you
	- You just define what you need 
	- Spring decides when and how to create it

IoC in Spring
- Implemented via the Spring Container (Application Context)
- Container manages beans (objects annotated )

Everytime you change something COMMIT IT FIRST, SO YOU CAN ROLLBACK LATER
# References

