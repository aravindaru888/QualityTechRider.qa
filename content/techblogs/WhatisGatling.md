---
title: Gatling
date: 2023-01-20T08:00:00
lastmod: 2024-05-07T18:05:00
images: 
- /img/gatling/Gatling-logo-RVB.png
description: Gatling.
tags: ['web-dev', 'hugo', 'guide']
---

Gatling DSL (Domain-Specific Language) is a specialized programming language designed specifically for defining and running performance tests with Gatling, an open-source load testing tool. The DSL allows testers and developers to write expressive, concise, and readable performance test scenarios in Scala, which is the language Gatling is built on. The Gatling DSL abstracts much of the complexity involved in writing performance tests, making it easier to define scenarios, configure requests, and perform checks.

Key Features of Gatling DSL are

### Scenario Definition:
Define the sequence of HTTP requests and actions that simulate user behavior.
### HTTP Requests:
Configure GET, POST, PUT, DELETE, and other HTTP requests.
### Checks:
Validate responses with assertions, such as checking status codes, response times, and specific data in the responses.
### Feeders:
Provide dynamic data to the tests using feeders, which can read data from CSV files, JSON files, and other sources.
### Injection Profiles:
Define how users are injected into the system over time, such as ramping up users gradually or starting with a burst of users.
### Reports:
Generate detailed and graphical reports of the test results, showing metrics like response times, request counts, and error rates.


Example of Gatling DSL
Here's a simple example to demonstrate the usage of the Gatling DSL:

## 
	import io.gatling.core.Predef._
	import io.gatling.http.Predef._

	class MySimulation extends Simulation {

	  // Define the HTTP protocol configuration
	  val httpProtocol = http
		.baseUrl("http://example.com") // Base URL for all requests
		.acceptHeader("application/json") // Default headers
		.userAgentHeader("Gatling")

	  // Define a feeder for dynamic data
	  val feeder = csv("data/users.csv").circular

	  // Define the scenario
	  val scn = scenario("My Scenario")
		.feed(feeder) // Use the feeder for dynamic data
		.exec(http("Get User")
		  .get("/user/${userId}") // Dynamic URL based on feeder data
		  .check(status.is(200)) // Check that the response status is 200
		  .check(jsonPath("$.name").is("${userName}")) // Check the JSON response
		)

	  // Set up the simulation with injection profile
	  setUp(
		scn.inject(
		  atOnceUsers(10), // Inject 10 users at once
		  rampUsers(100).during(10.seconds) // Ramp up to 100 users over 10 seconds
		).protocols(httpProtocol) // Use the HTTP protocol configuration
	  )
	}

Explanation
HTTP Protocol Configuration: Sets the base URL and default headers for the HTTP requests.
Feeder: Reads dynamic data from a CSV file to be used in the requests.
Scenario Definition: Defines a scenario named "My Scenario" that performs a GET request to /user/${userId}, where ${userId} is a placeholder for dynamic data from the feeder. The scenario includes checks to validate the response status and specific data in the JSON response.
Injection Profile: Defines how users are injected into the simulation. In this example, 10 users are injected at once, and then 100 users are ramped up over 10 seconds.
Simulation Setup: Sets up the simulation with the defined scenario and HTTP protocol configuration.
Benefits of Gatling DSL
Readability: The DSL makes it easy to read and understand performance test scenarios, even for those who are not familiar with Scala.
Expressiveness: The DSL provides a rich set of features to express complex scenarios and checks concisely.
Reusability: Scenarios, feeders, and configurations can be reused across different tests, promoting code reuse and maintainability.
Extensibility: Custom actions and checks can be implemented in Scala, allowing for advanced customization and extension of the DSL.
The Gatling DSL is a powerful tool that simplifies the creation and management of performance tests, enabling teams to effectively simulate and analyze user behavior under load.








