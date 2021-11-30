# Postman-Automation

Repo for storing .json Backup files on all BE Automation tests in Postman

# For every Collection in our Postman App there are separate Branches. The naming of branches are self exploratory. 
## For Sanity tests we use Sanity-tests-Collection.
## For Smoke tests we use Smoke-tests-Collection.

[Here you can find the whole documentation in Notion](https://www.notion.so/POSTMAN-Design-doc-Best-Practices-and-Style-Guide-8467474eadae4d9fbd3d66ae3da5b481)
=================================

![postman logo](https://github.com/OlliePin/Postman-repo/blob/main/postman-logo-vert-2018.jpeg?raw=true)

# Postman Automation tests Style Guide

## Table of Contents

  1. [Introduction](#introduction)
  1. [Requests Naming](#requests-naming)
  1. [Naming Conventions](#naming-conventions)
  2. [Declaration of Variables](#declaration-of-variables)
  3. [Coding Standards](#coding-standards)
  4. [Libraries](#libraries)
  5. [Methods](#methods)
  6. [Redundancy](redundancy)




## Introduction

  A style guide for Postman is a way to foster authenticity by containing instructions for all QA Engineers creating content for our company.
  Since our InPlayer team was led by Airbnb Coding standard we made a small mix of Airbnb and our Postman standard in practice🙂 
  By creating a detailed brand style guide, we ensure that our content has a set of standards that defines our Postman Automation branding. We also need to 
  be  ensured that our content is consistent, recognisable and more enjoyable / easy to use (especially when we do review to each other)
  
  
## Requests Naming

  Request name and appending Service in brackets, e.i Authenticate MP (v2/accounts), (v2/items) etc..
  
  
## Naming Conventions

  camelCaseSmoke - for Smoke
  camelCaseLiveLike - for Feature LiveLike
  authTokenSmokeLiveLike - Token for Smoke suite for LiveLike functionality.
  
  ```diff
  - // bad
  const auth_token_smoke = 15;
  function c() {}

  + // good
  const authTokenSmoke = 15;
  function thisIsMyFunction() {}
  
  Note: 
  - Please use Collection variables if and only if you need the value from previous requests, otherwise please avoid and use Local variables
  ```
## Declaration of Variables

  Variable for parsed JSON Response should be declared as CONST and placed in first line in tests Tab
  
  ![json const](https://github.com/OlliePin/Postman-repo/blob/main/CONST%20JSON%20.png?raw=true)
  
  Use **LET** variables inside Loops
  
  - **var** can be re-declared and updated
  - **let** can be updated but not re-declared
  - **const** value cannot be re-declared and cannot be updated
  - **var** have a global scope and function-scope, **Let** and **Const** provides block-scoped in JS

  ![for loop](https://github.com/OlliePin/Postman-repo/blob/main/Let_Variable_inside_Loops.png?raw=true)
  
  Use meaningull variable names
  
## Coding Standards

  DateTime format should be define using  ***RFC 3339 - 2019-10-12T07:20:50.52Z***

  Declaration of **Arrays**
  
  ```diff
  - // bad
  const items = new Array();

  + // good
  const items = [];
  ```
  
## Libraries

  Use **Moment.js** library when format and display dates in Postman
  
  ![library](https://github.com/OlliePin/Postman-repo/blob/main/Library_Moment.png?raw=true)
  
  **Chai.js** we already used as assertion library
  
  **Faker.js** library might be used for generating fake data
  
## Methods

  We should always used in Collection or Folder level in Pre-request Script tab. These methods can be recalled anywhere 
  in any child in collection (Folder, sub-folder, request)
  
  ![methods](https://github.com/OlliePin/Postman-repo/blob/main/Function_round.png?raw=true)
  
## Redundancy

  Delete Redundant code in the tests
  ```diff
  + CORRECT
  ```
  
  ![correct comment](https://github.com/OlliePin/Postman-repo/blob/main/Method_format_comments.png?raw=true)
  ```diff
  - WRONG
  ```
  ![wrong comment](https://github.com/OlliePin/Postman-repo/blob/main/Delete_Redundant_Code.png?raw=true)
  
  Delete Multi Line Comments from the tests Scripts in order to have a clear PR
  
  If there is single line comment explaining or reminding the Automation engineer what the particular code do, comment should be allowed.
