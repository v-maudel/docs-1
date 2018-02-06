---
title: Serverless apps. Architecture, patterns, and Azure implementation.
description: Serverless apps. Architecture, patterns, and Azure implementation. | Serverless design examples
keywords: Serverless, Microservices, .NET, Azure, Azure Functions
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 2/6/2018
ms.prod: .net
ms.technology: dotnet
ms.topic: article
---
# Serverless design examples

There are many design patterns that exist for serverless. This section captures some common scenarios that use serverless. What all of the examples have in common is the fundamental combination of an event trigger and business logic.

## Scheduling

Scheduling tasks is a common function. The following diagram represents a legacy database that doesn't have appropriate integrity checks. The database must be scrubbed periodically. The serverless function finds invalid data and cleans it. The trigger is a timer that runs the code on a schedule.

![Serverless scheduling](./media/serverless-scheduling.png)

## Command and Query Responsibility Segregation (CQRS)

Command and Query Responsibility Segregation (CQRS) is a pattern that provides different interfaces for reading (or querying) data and operations that modify data. It addresses several common problems. In traditional Create Read Update Delete (CRUD) based systems, conflicts can arise from high volume of both reads and writes to the same data store. Locking may frequently occur and dramatically slow down reads. Often, data is presented as a composite of several domain objects and read operations must aggregate data from different entities.

Using CQRS, a read might involve a special "flattened" entity that represents data the way it is consumed. The read is represented different than how it is stored. For example, although the database may represent a contact as a header record with a child address record, the read may involve an entity with both header and address properties. There are myriad approaches to providing the read model. It may be materialized from views. Update operations may be encapsulated as isolated events that then trigger updates to two different models. Separate models exist for reading and writing.

![CQRS example](./media/cqrs-example.png)

Serverless can accommodate the CQRS pattern by providing the segregated endpoints. One serverless function accommodates queries or reads, and a different serverless function or set of functions handles update operations. Front-end development is simplified to connecting to the necessary endpoints and processing of events is handled on the backend. This model also scales well for large projects because different teams may work on different operations.

## Event-based processing

In message-based system, events are often collected in queues or publisher/subscriber topics to be acted upon. These events can trigger serverless functions to execute a piece of business logic. An example of event-based processing is event-sourced systems. An "event" is raised to mark a task as complete. A serverless function triggered by the event updates the appropriate database document. A second serverless function may use the event to update the read model for the system. [Azure Event Grid](/azure/event-grid/overview) provides a way to integrate events with functions as subscribers.

## File triggers and transformations

![Serverless file triggers and transformations](./media/serverless-file-triggers.png)

## Asynchronous background processing

## Asynchronous messaging

## Web apps and APIs

![Serverless web API](./media/serverless-web-api.png)

## Data pipeline

![Serverless data pipeline](./media/serverless-data-pipeline.png)

## Stream processing

![Serverless stream processing](./media/serverless-stream-processing.png)

## API gateway

![Serverless API gateway](./media/serverless-api-gateway.png)

## Recommended Resources

>[!div class="step-by-step"]
[Previous] (./serverless-architecture-considerations.md)
[Next] (../azure-serverless-platform/index.md)