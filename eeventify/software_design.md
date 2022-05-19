<!-- omit in toc -->
# Software Design Eeventify

<!-- omit in toc -->
## Table of contents

- [1. Entity Relationship Model](#1-entity-relationship-model)
- [2. Software Architecture](#2-software-architecture)

## 1. Entity Relationship Model

![Entity Relationship Model](/images/er-model_eeventify_v1.png)

In order to provide the required functionality established in the project's user stories, Eeventify must support the following entities:
* **User** entities to store information about the user as well as users they are friends with, which events they own and/or are participating in and which interests they have;
* **Event** entities that contains information about events organized by user, which interests it is linked to and which chat session belongs to that particular event;
* **Chat** session entities that keeps track of to which event it belongs and which chat messages belong to it;
* **Chat message** entities that contain the content of the message, a timestamp when the message was sent, which chat session they belong to and who the author of the message is;
* **Interest** entities that contain a name and description of a particular interest and can be coupled with user entities and event entities.

[⬆️ Back to Table of Contents](#table-of-contents)

## 2. Software Architecture

![Software Architecture diagram version 1](/images/soft-architecture_eeventify_v1.png)  
*First version of Software Architecture Diagram for Eeventify*

The Eeventify application has been designed as a microservices architecture. This means the application is comprised of multiple loosely coupled and collaborating services. Advantages of this approach are that it improves maintainability and testability, is independently deployable and scalable and it facilitates easy integration of multiple technologies (for example a combination of SQL and NoSQL databases). Communication between front-end and back-end will be performed through REST and WebSocket protocols.

Eeventify consists of the following services:
* User Service
* Event Service
* Interest Service
* Chat Service

An API gateway is utilized so that the client application does not have to communicate with all the different services directly but can do so through a single interface. This also makes it easier to make changes to the architecture at a later stage, as the client application has no knowledge of what happens "behind" the gateway.

Each service has its own database and if it needs data from outside its domain to perform its function, it will contact the relevant service through the API gateway and request the needed data from the service that contains it. We have tried to minimize these dependencies in order to keep the different services as independent of each other as possible. In case the client application needs to collect data from the different domains it can contact each service separately to request the required data, combine it, and display it to the user.

![Software Architecture diagram version 2](/images/soft-architecture_eeventify_v2.png)  
*Final version of Software Architecture Diagram for Eeventify. Courtesy of: [Tjerk Zeilstra](https://github.com/TjerkZ)*

[⬆️ Back to Table of Contents](#table-of-contents)
