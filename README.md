<!-- omit in toc -->
# Reader's Guide for Semester 3 Portfolio

Written by: Jeffrey E.G. Derksen  
For course: S-DB-IPS3 and S-DB-GPS3  
Class: S3-DB01  
Coaches: Bert Aarts, Samuil Angelov and Leon van Bokhorst  
Date: 6 April 2022  
Version: 2  

Portfolio for semester 3 of the bachelor's program of IT from Fontys University of Applied Sciences.

<!-- omit in toc -->
## Version control

| Version | Changes |
|---------|---------|
| 1 | Initial version. |
| 2 | * Updated version of [Cultural Differences research](#21-cultural-differences)<br>* Extended [section 3](#3-individual-project-collecticats): explanation choice for Java and learning process<br>* Added [section 4.2](#42-cicd) about CI/CD within group project |

<!-- omit in toc -->
## Table of contents

- [1. Introduction](#1-introduction)
- [2. Research](#2-research)
  - [2.1. Cultural differences](#21-cultural-differences)
  - [2.2. Ethics](#22-ethics)
  - [2.3. Security](#23-security)
  - [2.4. Research 4](#24-research-4)
- [3. Individual Project (CollectiCats)](#3-individual-project-collecticats)
  - [3.1. Software design](#31-software-design)
- [4. Group Project (Eeventify)](#4-group-project-eeventify)
  - [4.1. Software design](#41-software-design)
  - [4.2. CI/CD](#42-cicd)
- [5. Reflection](#5-reflection)

## 1. Introduction

This document serves as the Reader's Guide for my semester 3 portfolio of the bachelor's program of IT from Fontys University of Applied Sciences. The portfolio contains the products I have developed during the semester and with which I prove that I have gained sufficient knowledge to fulfil the requirements set in the learning outcomes. This guide provides a brief summary of each product and section, and points the reader towards the files which contain the fully worked-out versions of the subject.

[⬆️ Back to Table of Contents](#table-of-contents)

## 2. Research

### 2.1. Cultural differences

For the subject of cultural differences I have done some research about what culture is and what are well-known dimensions on cultural differences. I have also written about my personal experiences with cultural differences. This product helps prove my proficiency at learning outcome 5: Cultural differences and ethics.  
[View file](/research/cultural_differences.md)

### 2.2. Ethics

Placeholder

### 2.3. Security

Placeholder

### 2.4. Research 4

Placeholder

[⬆️ Back to Table of Contents](#table-of-contents)

## 3. Individual Project (CollectiCats)

![CollectiCats logo](images/CollectiCats_logo_trans.png)

Inspired by: [CryptoKitties](https://www.cryptokitties.co/)

CollectiCats is my individual project and is a web based collecting/trading game where players can collect virtual cats and trade them with each other. These cats have unique properties as a result of their genes. Try to collect as many special and rare cats as you can!

I have made use of the SCRUM framework while working on this project and chose Taiga.io as the tool to help me manage this process. I have chosen to divide the project into five sprints of three weeks each.  
[View project management on Taiga.io](https://tree.taiga.io/project/jeffrey_derksen-s3-individual)

A good software engineer can quickly adapt to and utilize new technologies, and it is something I personally really enjoy as well. After using C#/.NET for the majority of the last two semesters and also making use of it for the [Eeventify](#4-group-project-eeventify) application, I have chosen to write the back-end for the CollectiCats application in Java with the Spring framework. As I had no prior experience with writing code with Java, I followed a number of tutorials and guides to get myself acquainted with the language, the framework and the microservices architecture. These are the following:

- [Spring Boot Microservices Level 1: Communication](https://www.youtube.com/watch?v=y8IQb4ofjDo&list=PLqq-6Pq4lTTZSKAFG6aCDVDP86Qx4lNas) by Jet Brains on YouTube
- [Accessing Data with MongoDB](https://spring.io/guides/gs/accessing-data-mongodb/) by Spring
- [Accessing MongoDB Data with REST](https://spring.io/guides/gs/accessing-mongodb-data-rest/) by Spring

### 3.1. Software design

For the CollectiCats application I have made a user stories, an entity relation model and a software architecture diagram. These diagrams/models and related information can be found in the software design document.

[⬆️ Back to Table of Contents](#table-of-contents) | [📄 View file](/collecticats/software_design.md)

## 4. Group Project (Eeventify)

Eeventify is the name of the group project developed in collaboration with two teams from the Oulu University of Applied Sciences (OAMK) located in Oulu, Finland. It is an application that helps people find others who share similar interests to theirs and provides a platform to organize, discover and join events (online *and* in person) that correspond to their interests.

### 4.1. Software design

For the CollectiCats application I have made an entity relation model and a software architecture diagram. These diagrams/models and related information can be found in the software design document.  

[⬆️ Back to Table of Contents](#table-of-contents) | [📄 View file](/eeventify/software_design.md)

### 4.2. CI/CD

For the Eeventify project I took up development of the CI/CD workflow together with another student. He took responsibility for the continues deployment, while I worked on continuous integration and delivery. In order to achieve this I made use of GitHub Actions, a CI/CD platform offered by the GitHub team that integrates directly with the source code repository. I had never used this platform before or even made use CI/CD of any kind, but the [documentation](https://docs.github.com/en/actions) proved quite helpful and GitHub provides several useful template workflows for different kind of projects and goals, such as building a .NET project or building and publishing a Docker image.

With these tools I have written a workflow for each Eeventify service that:
- Builds the project and runs unit tests;
- Generates a OpenAPI/Swagger documentation file;
- Pushes the generated documentation file to the repository containing all documentation files;
- Builds a Docker image;
- Publishes the image to DockerHub.

<figure>
    <img src="/images/eeventify_cicd1.png"
         alt="Screenshot of CI/CD workflow for Eeventify">
    <figcaption>Example of a CI/CD workflow run of Eeventify's user service.</figcaption>
</figure><br><br>

This workflow runs on each push to the main branch and for each pull request. Some of the steps are skipped depending on the context in which the workflow is executed. For example, the docker image should not be published to DockerHub if the workflow runs as part of a pull request check.

I believe that I learned a lot about CI/CD while setting these workflows up for the Eeventify project and that this helps prove my proficiency at learning outcome 4: CI/CD.

[⬆️ Back to Table of Contents](#table-of-contents) | [📄 View file](https://github.com/Eeventify/user-service/blob/main/.github/workflows/main.yml)

## 5. Reflection

This section will be populated near the end of the semester.

[⬆️ Back to Table of Contents](#table-of-contents)
