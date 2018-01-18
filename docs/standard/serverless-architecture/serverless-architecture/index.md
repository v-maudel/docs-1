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

The full serverless backend is ideal for several types of scenarios, especially when building new or "green field" applications. An application with a large surface area of APIs may benefit from implementing those APIs as serverless functions. Apps that are based on microservices architecture are another example that could be implemented as a full serverless backend. The microservices communicate over various protocols with each other.

### Monoliths and “starving the beast”

### Web apps

### Mobile back-ends

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
