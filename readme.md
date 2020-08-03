# ApiOmat base for Spring Microservices 

Base package for ApiOmat Microservices based on the Spring framework

## Starting
### Install locally:
    mvn install -Dgpg.skip=true
### Install in maven central
    mvn clean deploy
### Maven Project Structure
This Maven project consists of the following pom.xml files:
1. pom.xml in repository root which is the meta-pom for deploying the actual poms
2. pom.xml in spring-base-dependencies that defines all the dependency versions
3. pom.xml in spring base which is the "real" spring-base-pom and which will be integrated into the projects (it actually just contains the dependency management) 

The parent pom basically contains only the dependency management. The needed dependencies themselves need to be included within the projects pom.xml .