---
title: Serverless apps. Architecture, patterns, and Azure implementation.
description: Serverless apps. Architecture, patterns, and Azure implementation. | Serverless architecture
keywords: Serverless, Microservices, .NET, Azure, Azure Functions
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 12/21/2017
ms.prod: .net
ms.technology: dotnet
ms.topic: article
---
# Serverless architecture

There are many approaches to using serverless architectures. This chapter explores examples of common architectures that integrate serverless. It also covers concerns that may pose additional challenges or require extra consideration when implementing serverless. Finally, several design examples are provided that illustrate various serverless use cases.

## Serverless architecture examples

Some projects may benefit from taking an "all-in" approach to serverless. Applications that rely heavily on microservices may implement those using serverless technology. The majority of apps are hybrid, following an N-tier design and using serverless where it makes sense. To help make sense of these scenarios, this section walks through some common architecture examples that use serverless.

### Full serverless backend

The full serverless backend is ideal for several types of scenarios, especially when building new or "green field" applications. An application with a large surface area of APIs may benefit from implementing those APIs as serverless functions. Apps that are based on microservices architecture are another example that could be implemented as a full serverless backend. The microservices communicate over various protocols with each other. Specific scenarios include:

* API-based SaaS product
* App focused on integration between services (example: airline booking application)
* Processes that run periodically (example: timer-based database clean-up)
* Apps that are focus on data transformation (example: import triggered by file upload)
* Mobile back-ends
* Internet-of-Things (IoT) apps

### Monoliths and “starving the beast”

A common challenge is migrating an existing monolithic application to the cloud. The least risky approach is to "life and shift" entirely onto virtual machines. Many shops prefer to use the migration as an opportunity to modernize their code base. A practical approach to this is called "starving the beast." In this scenario, the monolith is migrated "as is" to start with. Then, select services are modernized. In some case the signature of the service is identical to the original, it simply is hosted as a function. Clients are updated to leverage the new service rather than the monolith endpoint. In the interim, steps such as database replication enable microservices to host their own storage even when transactions are still handled by the monolith. Eventually, clients are migrated onto the new services and the monolith is "starved" until all functionality has been replaced. The combination of serverless and proxies can facilitate much this migration.

To learn more about this approach, watch the video [Bring your app to the cloud with serverless Azure Functions](https://channel9.msdn.com/Events/Connect/2017/E102).

### Web apps

### Mobile back-ends

The event-driven paradigm of serverless apps makes them ideal as mobile back-ends. The mobile device triggers the events and the serverless code executes to satisfy requests. Leveraging a serverless model empowers developers to enhance business logic without necessarily having to deploy an application update. The serverless approach also enables teams to share endpoints and work in parallel.

### Internet of Things (IoT)

### Command and Query Responsibility Segregation (CQRS)

## Serverless architecture considerations

### Managing state

### Long-running processes

### Database updates and migrations

### Scaling

### Monitoring, tracing, and logging

### Inter-service dependencies

### Managing failure and providing resiliency

### Versioning and green/blue deployments

## Serverless Design Examples

### Scheduling

### Event-based processing

### File triggers and transformations

### Asynchronous background processing

### Asynchronous messaging

### Web apps and APIs

### Data pipeline

### Stream processing

### API gateway

## Recommended Resources

>[!div class="step-by-step"]
[Previous] (../architecture-approaches/index.md)
[Next] (../azure-serverless-platform/index.md)
