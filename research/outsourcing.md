# Research report: Optimizing for outsourcing

Written by: Jeffrey E.G. Derksen  
For course: S-DB-GPS3  
Class: S3-DB01  
Date: 11 June 2022  
Version: 1  

In the field of software engineering, a developer seldom works on a project alone. When you develop a large application or other comprehensive software project, you most commonly work in a team. And software projects or components may very well be used by outside developers to incorporate into their project as a dependency. In these situations it is very important that the code that you write is clear and logically structured according to established style guidelines, and that you provide useful and detailed documentation alongside your code. When this is properly executed, a team member or even a developer from the other side of the world with no prior knowledge of your project can easily utilize, customize, and expand your code. In this research report, I will seek to find answers to the following **main research question:**

> How can you, as a software developer, best optimize your code/application for seamless outsourcing

This research project has been performed partly as a joint research with a fellow student, [Robin van Hoof](https://github.com/RobinvHoof). We chose the same topic and have agreed to participate as a test subject in each others research project by building a front end proof of concept application for a back end application we have developed ourselves. Afterwards we provided feedback on the process. Was the code and documentation clear and straightforward, did we get stuck during development and had to contact the other for help and/or clarification, etc.

During this research project I have made use of the [DOT framework](https://ictresearchmethods.nl/The_DOT_Framework) to guide my process and to assist me with acquiring the right information and drawing conclusions from it. I have made use of the following methods:
- Library: best good and bad practices, design pattern research, literature study
- Field: survey
- Showroom: peer review, static program analysis

## Sub-questions

In order to answer the main research question, I have broken the problem down into smaller sub-questions:

- Wat are some best practices and design patterns for making your code clear and understandable?
- How to implement these practices into my own software project?
- Is another developer able to utilize my software without requiring my assistance?
- Are there points for further improvement?

## Best practices and design patterns for clear and understandable code

Software quality is an important factor of the suitability of your code for outsourcing. There are several ways to increase 

### Using a style guide

For enhanced 

## Implementing best practices and design patterns

### Documentation

I have set up two kinds of documentation for the back end of my application. One details setting up the application by using Docker Compose, and the other contains information about the API endpoints that the back end provides, such as: routes, parameters and response bodies.

### Static Code Analysis

To further monitor and improve my code quality, I have implemented static code analysis into the continuous integration process for my application. The software I have chosen for this is SonarCloud. This platform offers easy integration with GitHub and checks for a plethora of possible quality issues, such as: bugs, vulnerabilities, code smells, test coverage, and duplication of code.

![Screenshot of SonarCloud static code analysis overview](../images/sonarcloud_overview.png)  
*Overview of static code analysis for some of my project's services in SonarCloud.*

## Outsourcing experiment

To test the effect of the measures taken to improve the quality and documentation of my code, I offered my application to my fellow student and test subject, Robin. [hopefully he manages to make something of it]

## Experiment feedback and conclusions

After the experiment concluded and Robin finished his proof of concept of a front end for my application, I asked him for feedback and requested that he take a short survey that I made about the quality of my documentation. A PDF version of the survey form can be found [here](../images/Survey%20-%20Quality%20of%20Documentation.pdf).

The results...

## Sources

- Canvas: [Code Quality Analysis](https://fhict.instructure.com/courses/12078/pages/code-quality-analysis?module_item_id=749946)
- [DOT framework](https://ictresearchmethods.nl/The_DOT_Framework)
- [Java Style Guide by Google](https://google.github.io/styleguide/javaguide.html)
