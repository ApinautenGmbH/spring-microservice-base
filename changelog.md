# Changelog

This document contains some helpful information to update your project's spring-base version.

## Update 1.2.5 to 2.0.0

With version 2.0.0 the spring-base pom.xml only contains the dependency management (versioning of dependencies). 
This means that you have to include all needed dependencies into your project's pom.xml by yourself, because the spring-base pom.xml doesn't deliver them. 

### Recommended Way of Migration

- Navigate to the root directory of your Maven project and execute the following command to retrieve a list of resolved dependencies:

    mvn dependency:list

- Increase the version of the parental spring-base dependency in your project's pom.xml to 2.0.0



- Resolve your compile errors by putting the needed dependency from your list (step 1) to your project's pom.xml (one by another)



- To find unused declared dependencies and used undeclared dependencies you can use the following command to keep your pom.xml clean: 

    mvn dependency:analyze