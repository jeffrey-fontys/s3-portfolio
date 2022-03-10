# Software Design

## Table of contents

1. [Entity Relationship Model](#entity-relationship-model)

## Entity Relationship Model

![Entity Relationship Model](/images/er-model-collecticats-v1.png)

## Software Architecture

![Software Architecture diagram](/images/architecture_collecticats_v1.png)

The CollectiCats application has been designed as a microservices architecture. This means the application is comprised of multiple loosely coupled and collaborating services. Advantages of this approach are that it improves maintainability and testability, is independently deployable and scalable and it facilitates easy integration of multiple technologies (for example a combination of SQL and NoSQL databases). Communication between front-end and back-end will be performed through REST.

CollectiCats consists of the following services:
* User Service
* Cat Service
* Breeding Service
* Trading Service

An API gateway is utilized so that the client application does not have to communicate with all the different services directly but can do so through a single interface. This also makes it easier to make changes to the architecture at a later stage, as the client application has no knowledge (and does not need to have) of what happens "behind" the gateway.

Each service has their own database and if they need data from outside their domain to perform their function, they will contact the relevant service and request the needed data through them.
