---
title: Serverless apps. Architecture, patterns, and Azure implementation.
description: Serverless apps. Architecture, patterns, and Azure implementation. | Serverless architecture considerations
keywords: Serverless, Microservices, .NET, Azure, Azure Functions
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 1/19/2018
ms.prod: .net
ms.technology: dotnet
ms.topic: article
---
# Serverless architecture considerations

Adopting a serverless architecture does come with certain challenges. This section explores some of the more common considerations to be aware of. All of these challenges have solutions. As with all architecture choices, the decision to go serverless should be made only after carefully considering the pros and cons. Depending on the needs of your application, you may decide a serverless implementation is not the right solution for certain components.

## Managing state

Serverless functions, as with microservices in general, are stateless by default. Avoiding state enables serverless to be ephemeral, to scale out, and to provide resiliency without a central point of failure. In some circumstances, business processes require state. If your process requires state, you have two options. You can adopt a model other than serverless, or interact with a separate service that provides state. Adding state can complicate the solution and make it harder to scale, and potentially create a single point of failure. Carefully consider whether your function absolutely requires state. If the answer is "yes," determine whether it still makes sense to implement it with serverless.

There are several solutions to adopt state without compromising the benefits of serverless. Some of the more popular solutions include:

* Use a temporary data store or distributed cache, like Redis
* Store state in a database, like SQL or CosmosDB
* Handle state through a workflow engine like durable functions

The bottom line is that you should be aware of the need for any state management within processes you are considering to implement with serverless.

## Long-running processes

Many benefits of serverless rely on the processes being ephemeral. Short run times make it easier for the serverless provider to free up resources as functions terminate and share functions across hosts. Most cloud providers limit the maximum time your function can run to around 10 minutes. If your process may take longer, you might consider an alternative implementation.

There are a few exceptions and solutions. One solution may be to break your process into smaller components that individually take less time to run. If your process runs long due to dependencies, you can also consider an asynchronous workflow using a solution like durable functions. Durable functions pause and maintain the state of your process while it is waiting on an external process to finish. Asynchronous handling reduces the time the actual process runs.

## Startup time

## Database updates and migrations

## Scaling

## Monitoring, tracing, and logging

## Inter-service dependencies

## Managing failure and providing resiliency

## Versioning and green/blue deployments

>[!div class="step-by-step"]
[Previous] (./index.md)
[Next] (./serverless-design-examples.md)