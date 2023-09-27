
# Preconditions & Hints

Timebox: **Maximum 3 hours**

Please fork this repository and share your approach via a link to your repository.

# Story for Java Backend Developer

## User Story

As a service technician I would like to get the standard minimum outdoor temperature for an installation address in France, 
so that I can scale the heating system properly.

## Background /  Description
We need to add a new microservice to our existing Vaillant API environment to get the standard minimum outdoor temperature for 
a given address that can be used by our service technicians to recommend a heatpump-based heating system to the customer.

The service should take an address as argument and use an arbitrary maps API (like OSM or Google Maps) to retrieve the altitude in meters.
In the next step the altitude / postal code has to be compared with our data from the country (France) to finally calculate the temperature 
by adding the temperature offset for the given altitude to the temperature for the given postal code.
Because the data may change often, it should be stored in a database to avoid unnecessary redeployments of the application.

## Definition of Ready

| Done | Content                                                                               |
|------|---------------------------------------------------------------------------------------|
| ✅    | Datasets of standard minimum outdoor temperatures are provided (see: datasets/*.json) |

## Definition of Done

* Service is tested adequately with a testing framework of your choice
* All changes are committed and pushed to a Git repository
* The application can be built without errors and produces a potentially shippable artifact (e.g. a JAR or WAR)

## Acceptance criteria

* The service is written in Java and Spring (no further constraints)
* The service exposes its functionality via a RESTful API where the request/response is encoded in JSON.
* The API accepts an address as argument - either as a single or split into multiple parameter (will only be tested with french addresses)
* The API returns the altitude and the standard minimum outdoor temperature as response.
* Mapping data between postal codes / altitudes / temperatures is imported and stored within a database of your choice
* The application can be built using either Maven or Gradle and should produce a potentially shippable artifact (JAR/WAR)

## Out of scope

* Any kind of authentication or authorization (e.g. OAuth2)

## Nice to Have

* The artifact resulting from the build of the application is a self-contained JAR, that doesn't require running a separate servlet container.