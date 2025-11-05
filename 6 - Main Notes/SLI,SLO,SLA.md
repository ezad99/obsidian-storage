2024-06-18 16:51

Status: #new

Tags: [[SRE (Site Reliability Engineering)]]

# SLI,SLO,SLA
The steps of SRE are:
- Define availability
- Level of availability
- Plan in case of failure

100% availability is more impossible the bigger the software

SLA (Service Level Agreement)
	A Contract
	An expectation of the performance and reliability of an app and the consequences of not meeting them
	The legal language that accompany the dollars that we spend when we buy a service

To ensure we achieve our SLA's we set some SLO's

SLO (Service Level Objective)
	They define the desired performance and reliability standards of a service:
		Examples:
			Availability SLO: 99.9% uptime
			Latency SLO: 95% of requests should be completed within 100 milliseconds
			User Authentication SLO: 99% of user authentication requests should complete within 300 milliseconds

To keep track on how well we are meeting our SLO's we need SLI's

SLI (Service Level Indicator)
	Actual metrices to measure our compliance with our SLO
	Examples:
		Availability: Proportion of time a service is up and running
		Latency: Time taken to respond to a request
		Error Rate: Percentage of failed requests
		Throughput: Number of requests processed in a given time period

Example Scenario
SLI: 99% of HTTP request to the /api/v1 resource endpoint return a 200 status code within 300ms
SLO: 99% of requests must complete within 300ms over a rolling 30-day window
SLA: The service will have 99.5% availability per month. If this is not met, the customer will receive a service credit of 10% of the monthly fee.
# References

