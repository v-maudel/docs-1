---
title: Serverless apps. Architecture, patterns, and Azure implementation.
description: Serverless apps. Architecture, patterns, and Azure implementation. | Serverless design examples
keywords: Serverless, Microservices, .NET, Azure, Azure Functions
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 1/19/2018
ms.prod: .net
ms.technology: dotnet
ms.topic: article
---
# Serverless design examples

There are many design patterns that exist for serverless. This section captures some common scenarios that use serverless. What all of the examples have in common is the fundamental combination of an event trigger and business logic.

## Scheduling

Scheduling tasks is a common function. The following diagram represents a legacy database that doesn't have appropriate integrity checks. The database must be scrubbed periodically. The serverless function finds invalid data and cleans it. The trigger is a timer that runs the code on a schedule.

![Serverless scheduling](./media/serverless-scheduling.png)

## Event-based processing

In message-based system, events are often collected in queues or publisher/subscriber topics to be acted upon. These events can trigger serverless functions to execute a piece of business logic. An example of event-based processing is event-sourced systems. An "event" is raised to mark a task as complete. A serverless function triggered by the event updates the appropriate database document. A second serverless function may use the event to update the read model for the system.

> TODO: event-based diagram

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