<!-- omit in toc -->
# Software Design CollectiCats

<!-- omit in toc -->
## Table of contents

- [1. User Stories](#1-user-stories)
- [2. Entity Relationship Model](#2-entity-relationship-model)
- [3. Software Architecture](#3-software-architecture)
- [4. API Endpoints](#4-api-endpoints)

## 1. User Stories

A number of user stories have been formulated to describe and help verify the intended functionality of the CollectiCats application.

* As a player I want to be able to own several virtual cats, because collecting things is fun and cats are likable creatures.
* As a player I want to be able to see an overview of the cats I own, so that I know which cats I have and can interact with them.
* As a player I want to be able to see detailed information about a cat of my choosing, so that I can make an informed decision with regards to breeding and/or trading.
* As a player I want to be able to search all cats on the platform based on information such as ID or specific properties, so that I can discover candidates for trading.
* As a player I want to be able to create a new cat by letting two of my cats breed with one another, so that I can receive a new cat.
* As a player I want my new cat to have properties of both parents and be unique, so that I can breed cats for specific properties that I like and/or are valuable.
* As a player I want to have a chance that my new cat will turn out to be a special cat, because that is special to have and valuable to trade.
* As a player I want to be able to trade one of my cats with one of another user, so that I can obtain the cats (and the properties) that I would like to own and/or breed with.

[⬆️ Back to Table of Contents](#table-of-contents)

## 2. Entity Relationship Model

![Entity Relationship Model](/images/er-model-collecticats-v1.png)

The most important entities within CollectiCats are the User and the Cat entities. The User entity contains all the information bound to the users of the system (also referred to as the *player*), such as: name, password, email address and profile picture.

A player can own one or more virtual cats, the details of which are stored in the Cat entity. Each Cat entity also contains a DNA string, consisting of several gene pairs. The genes in these pairs determine which properties a Cat entity shows and this makes each entity unique and determines a cat's rarity level and special status. Genes can be either dominant or recessive, and it depends therefore on the combination which property will express itself as a result.

[⬆️ Back to Table of Contents](#table-of-contents)

## 3. Software Architecture

![Software Architecture diagram](/images/architecture_collecticats_v2.png)

The CollectiCats application has been designed as a microservices architecture. This means the application is comprised of multiple loosely coupled and collaborating services. Advantages of this approach are that it improves maintainability and testability, is independently deployable and scalable and it facilitates easy integration of multiple technologies (for example a combination of SQL and NoSQL databases). These advantages do come at a cost though, as this architecture pattern also increases complexity, consumes more resources, and requires complex orchestration to operate. For this application, a monolithic architecture might have performed equally well and would have likely been easier to develop, but the learning outcomes mandated a distributed software architecture and a microservices architecture seemed like a well fitting candidate.

CollectiCats consists of the following microservices:
* User Service
* Cat Service
* Breeding Service
* Trading Service

An API gateway is utilized so that the client application does not have to communicate with all the different services directly but can do so through a single interface. This also makes it easier to make changes to the architecture at a later stage, as the client application has no knowledge of what happens "behind" the gateway. The gateway makes use of a discovery server to find the current location of the services and communication is performed with the REST protocol.

Each service has their own database and if they need data from outside their domain to perform their function, they will contact the relevant service and request the needed data through them. In practice, most data gets aggregated in the front end part of the application. If I were to develop this application further in the future it might be possible to configure the API gateway to perform some or all of this aggregation.

The type of database system used is MongoDB. MongoDB is a NoSQL, document-oriented database program. Advantages of this system is that it is very easy to set up and to make changes to the structure during the development process, because a document does not have to have a predefined structure and documents can even have varying amounts and types of properties. It is also very easy to scale up and down for large scale applications, because it scales horizontally. However, it is generally considered less mature than SQL and when it comes to storing large amounts of data it can have issues with consistency and reliability. For my application these drawbacks are not particularly relevant because of the limited scale, and I wanted to gain some more experience working with a NoSQL database system as I have previously worked primarily with SQL based systems.

[⬆️ Back to Table of Contents](#table-of-contents)

## 4. API Endpoints

The CollectiCats client application communicates with the back-end services through the following endpoints:

| Path | Method | Description |
|------|--------|-------------|
| /users | GET | Get collection of users |
|        | POST | Create a new user |
| /users/{id} | GET | Get specific user information |
|             | PUT | Overwrite the user record with new information |
|             | PATCH | Overwrite specific fields in a user record |
|             | DELETE | Delete the specified user record |
| /cats | GET | Get collection of cats |
|       | POST | Create a new cat |
| /cats/{id} | GET | Get specific cat information |
|            | PUT | Overwrite the cat record with new information |
|            | PATCH | Overwrite specific fields in a cat record |
|            | DELETE | Delete the specified cat record |
| /breed |      | to be determined |
| /trade |      | to be determined |

[⬆️ Back to Table of Contents](#table-of-contents)
