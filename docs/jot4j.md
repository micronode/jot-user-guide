[JOT API]: jotapi.md

# Jot4j
Jot4j is a Java-based implementation of the JOT persistence layer. It aims to support multiple persistence backing services and provide a common interface for implementing the [JOT API].

## Overview
Jot4j includes a number of sub-projects that provide concrete implementations of persistence for various backing services. Initially support is provided for DynamoDB, but more will be added over time.

## Jot4j-dynamodb
The DynamoDB implementation makes use of the Single-table Design pattern, whereby multiple entities and relationships are modeled in a single DynamoDB table. This provides benefits in both performance and simplicity, allowing for greater decoupling of data models and better support for microservices architectures.

### Jot4j Mapper
Jot4j uses DynamoDB mapper annotations to define the entities managed in the single-table model. The following mapper objects are supported:

* Calendar
* Event
* Journal
* ToDo
* Availability
* Available
* Alarm
* Attachment
* Group
* Card
* CardOrg

### Global Search Indexes (GSI)
Jot4j uses three (3) Global Search Indexes to support data retrieval. These GSIs include:

* GSI1 - Indexed by entity type (e.g. `CALENDAR`, `VEVENT`, `VALARM`, etc.)
* GSI2 - Indexed by group and/or calendar
* GSI3 - Indexed by calendar component

### Jot4j Commands
Jot4j used the Command pattern to support operations on Mapper objects. The following commands are supported:

* CreateCalendar - create a new calendar definition
* UpdateCalendar - update the properties of an existing calendar definition
* DeleteCalendar - delete an existing calendar
* 