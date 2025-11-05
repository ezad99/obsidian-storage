2024-06-18 17:19

Status: #new

Tags: [[SRE (Site Reliability Engineering)]]

# Grafana
Grafana is:
	A open source analytics & interactive visualization web application 
	Allows you to transform the mountain of performance metric data collected from your applications into visualizations. Allows you to draw conclusions and make decisions to keep your application stack healthy

Features:
Visualization
	Grafana has a huge number of visualization options that are split into "panels"
	A panel is the lowest/most granular visualization building block in Grafana
		It is used to display data that has been queried from the data source connected to the panel
Alerting
	Grafana has built in support for a huge number of notification channels 
		such as email, slack etc
	To create an alert, create and configure an alert rule.
		The rule serves as a trigger for the alert
Annotations
	Grafana allows you to annotate directly on the graphs
	Allow us to mark important points on the graph
		Which acts as a reminder for further action of provide context for new member or to mark a special event on the graph
	Basically like writing a sticky note and placing it on the graph
Open Source
	Flexibility to develop and publish plugins

Data Sources
A Grafana Data Source is a database form which it can pull data

You just have to create a connection between the Grafana instance and the data source and provide a data query	

Grafana then pulls and displays the data from the data source at predefined/configurable intervals based on the query provided

Each data source supported by Grafana has a specific query editor for an optimal query writing experience
# References
