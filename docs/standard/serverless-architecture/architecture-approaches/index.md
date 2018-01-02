---
title: Serverless apps. Architecture, patterns, and Azure implementation.
description: Serverless apps. Architecture, patterns, and Azure implementation. | Architecture approaches
keywords: Serverless, Microservices, .NET, Azure, Azure Functions
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 12/21/2017
ms.prod: .net
ms.technology: dotnet
ms.topic: article
---
# Architecture approaches

Understanding existing approaches to architecting enterprise apps helps clarify the role played by serverless. There are many approaches and patterns that evolved over decades of software development, and all have their own pros and cons. In many cases, the ultimate solution may not involve deciding on a single approach but may integrate several solutions. Migration scenarios often involve shifting from one architecture approach to another through a hybrid approach.

## N-Tier applications

The N-Tier architecture pattern has existed for many years and simply refers to applications that separate various components of functionality into tiers. The most common implementation of this architecture involves:

* A presentation tier, for example a web app
* An API and/or data access tier, such as a REST API
* A data tier, such as a SQL database

This approach provides several benefits, including:

* Isolation of the database (often the frontend doesn't have direct access to the database backend)
* Reuse of the REST API (for example, mobile, desktop, and web app clients can all reuse the same APIs)
* Ability to scale out tiers independent of each other
* Refactoring isolation: one tier may be refactored without impacting other tiers

## Microservices

The term **microservices** has recently gained popularity. Although there is no universally accepted definition of microservices, there are many common traits of microservices architectures. Characteristics include:

* Applications are composed of several small services
* Each service runs in its own process
* Services are aligned around business domains
* Services communicate over lightweight APIs, typically using HTTP as the transport
* Services can be deployed and upgraded independently
* Services are not dependent on a single data store
* The system is designed with failure in mind, and the app may still run even when certain services fail

Microservices don't have to be mutual to other architecture approaches. For example, an N-Tier architecture may use microservices for the middle tier. It is also possible to implement microservices in a variety of ways, from virtual directories on IIS hosts to containers. The characteristics of microservices make them especially ideal for serverless implementations.

The pros of microservices architectures include:

* Refactoring is often isolated to a single service
* Services can be upgraded independently of each other
* Resiliency and elasticity can be tuned to the demands of individual services
* Development can happen in parallel across disparate teams and platforms
* It is easier to write tests for isolated services

Microservices come with their own challenges, including:

* Determining what services are available and how to call them
* Managing the lifecycle of services
* Understanding how services fit together in the overall application
* End-to-end testing of calls made across disparate services

Ultimately there are solutions to address all of these challenges, including tapping into the benefits of serverless that are discussed later.

## On-premises and Infrastructure-as-a-Service (IaaS)



## Platform-as-a-Service (PaaS)

## Software-as-a-Service (SaaS)

## Containers and Functions-as-a-Service (FaaS)

## Serverless

## Recommended resources

>[!div class="step-by-step"]
[Previous] (../index.md)
[Next] (../serverless-architecture/index.md)
