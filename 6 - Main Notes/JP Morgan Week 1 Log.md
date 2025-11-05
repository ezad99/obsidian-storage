2025-09-15 21:02

Status: #new

Tags: [[JP Morgan]], [[Log]]

# JP Morgan Week 1 Log
### Monday (15/9/25)
Benefits:
- £820 for WFH equipment
- 6% max contribution matching 
- Retail card

First meeting w/ Jonathan
- Able to WFH if needed to
- In locations with traders, the traders and SE's work together in the same team, which was uncommon a few years back
- XiaoTong has a level 3 CFA (Chartered Financial Analyst)
- Releases are done every week
	- The releases are managed by someone which is rotated between different members and teams over a certain period
	- Used to have one Central Release Manager but now the responsibility is divided due to expanding teams and timezone differences
- Start up with London team is everyday at 2pm
- Wednesday 
	- Work on a powerpoint to show 
- What Jonathan wants in a graduate:
	- Attitude
	- Passion to learn
	- Get everything I can from the program
	- Enjoy it
	- Get as much technical knowledge
	- Get up to speed as soon as possible
- Languages used in Team
	- Java (Primarily)
	- Python
- I should have one on one sessions with everyone in the team local and globally
- Checklist for this week:
	- Get setup
	- Commit to prod before end of week
- Overview of Role
	- 13th floor is Asset management while 12th floor is wealth management
	- There is 4 divisions:
		- Investment Banking
		- Retail Banking
		- Private Banking
		- Asset Management
	- We work in Asset Management
		- Essentially managing large pools of money for clients
		- Portfolio Managers are the people who make the investments
			- A few classes of investments
				- Equity 
				- Fixed-income
				- FX (Forex)
	- There are different platforms for all these classes but now they are trying to bring them together by syncing features
	- Front office: Portfolio Manager who places an order for the trade
	- Back office: Executes the trade
		- We build software to execute the trade either electronically or we put options in place so a human may handle it if deemed necessary
	- We work in cross trading where we handle all classes of investment
	- We get requests from traders, tech teams and even derivatives
	- We follow spotify's system of working in squads of 4-10 people
		- Our squad has 1 HK, 5 NY and all of glasgow
	- For the long term, having both tech and financial knowledge is a GREAT ASSET.

Setup Priority:
1. Intelij
2. Codebase, Jira, Bitbucket
3. Jenkins
4. logA(splunk)
5. Linux
6. Oracle Database

### Tuesday (16/9/25)
Things to learn
- Privileged sessions proxy (PSP)

There's a yearly DevOps conference
- 2500 drafts are given
- 167 get picked
- 600 attendees

Need to update new joiner guide on confluence
Seal ID: 35206

Meeting with Scot Baldry
- One way to network is to use content such as projects
- However this depends on the person, some people are more inclined to talk about personal stuff while others require specific projects to break the ice
- Understand the functional side of the business
- Understand how tech helps in the business
- Understand the primary drive behind tech
- Layer up little wins helps progressing alot
- Constantly upskill

### Wednesday (17/9/25)
Meeting with Karen Garner (Product Manager)
- Receives requests from multiple parties (stakeholders, traders, etc) and filters them
- Sets which tasks are priority
- Works under Steve Lipton
- Grows Assets under Management (AUM)
- Trade Workflow
	1. PM manages portfolio
	2. Raise orders to a trading desk to execute orders
	3. This may use an execution management system
	4. The booking then goes to another system

Meeting with Jonathan Hendrie
- PM: Makes orders
- Traders: Get the best possible price/deal through any means deemed viable
- OMS (Order Management System)
- Our job is to automate a traders job
- Money Order = Exchange to money
- Read about settlement and confirmation
- Trading strategies: MOC & MOO
- All our trading history is stored in a DB
- DNA is a team that uses that data and ML to look at the historical data and optimize our trades

SEP Program Overview
- There will be a lot of induction training
- Force for Good
	- 8 months
	- 6 Developers
	- Supported by associates and VPs
	- Project Champion (ED or MD)
	- 4 hours each work week including meeting and dev time
	- March - October
	- A showcase in November
- Common Phenomena's at work
	- Peter Principle
	- Dunning Kruger Effect
	- Imposter Syndrome
	- Curse of Knowledge
- Know when to ask questions, to soon or too late

Steps for projects in Intelij
- Open settings
- Then maven
- Change to bundled (3 maven)

Shift + F6 gives names suggestions for variables
GUIC -  Like dependency injection but not as hidden, easier to fix
# References

