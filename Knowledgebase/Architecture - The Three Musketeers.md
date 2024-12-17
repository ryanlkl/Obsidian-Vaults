---
summary: a pattern for developing software in a repeatable and consistent manner.
aliases:
  - 3 Musketeers
  - Three Musketeers
  - The Three Musketeers
href:
  - https://github.com/flemay/3musketeers
related:
  - "[[Software Architecture|Architecture]]"
tags:
  - standard
---
# Overview

3 Musketeers is a popular development pattern which makes use of three key tools for repeatable, consistent development. It leverages Make as an orchestration tool to test, build, run, and deploy applications using Docker and Docker Compose. The Make and Docker/Compose commands for each application are maintained as part of the application’s source code and are invoked in the same way whether run locally or on a CI/CD server.

# Structure

![[Architecture - 3 Musketeers - visual.png]]

1. Make
   The portability of Docker ensures you can execute the same tasks, the same way, on different environments like MacOS, Linux, Windows, and CI/CD tools.
2. Docker
    Make is a cross-platform build tool to test and build software and it is used as an **interface between the CI/CD server and the application code**. (Of course other tools like rake or ant can be used to achieve the same goal, but Makefile is pre-installed in many OS distributions makes it a convenient choice)
3. Compose
   It allows multiple Docker commands to be written as a single one, which allows our Makefile to be a lot cleaner and easier to maintain.

# Benefits

![[Architecture - 3 Musketeers - benefits visual.png]]

### Consistency

Run the same commands no matter where you are: Linux, MacOS, Windows, CI/CD tools that supports Docker like GitHub Actions, Travis CI, CircleCI, and GitLab CI.

### Control

Take control of languages, versions, and tools you need, and version source control your pipelines with your preferred VCS like GitHub and GitLab

### Confidence

Test your code and pipelines locally before your CI/CD tool runs it. Feel confident that if it works locally, it will work in your CI/CD server.

# EOF
___

%%
#note
created:: 2024-04-17
day:: Wednesday
week:: W16
month:: April
year:: 2024
%%
