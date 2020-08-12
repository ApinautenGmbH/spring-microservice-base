# Changelog

This document contains some helpful information to update your project's spring-base version.

## Update 1.2.5 to 2.0.0

With version 2.0.0 the spring-base pom.xml only contains the dependency management (versioning of dependencies). 
All the dependencies provided by spring-base 1.2.5 are no longer automatically included into your project. 

This means that you have to include all needed dependencies and plugins into your project's pom.xml by yourself, because the spring-base pom.xml doesn't deliver them.

More information about the spring-base structure can be found within the [readme.md](readme.md).

### Recommended Way of Migration

First update the version of your used spring-base to 2.0.0 by setting it as parent of your project's pom.xml

    <parent>
        <groupId>com.apiomat</groupId>
        <artifactId>spring-base</artifactId>
        <version>2.0.0</version>
    </parent>

Setting the spring-base as parent dependency implicitly pulls the defined dependency management from there.

If you explicitly want to define the dependency management you can do this by adding the following lines to your project's pom.xml:

    <dependencyManagement>
        <dependencies>
            <dependency>
                <groupId>com.apiomat</groupId>
                <artifactId>spring-base-dependencies</artifactId>
                <version>2.0.0</version>
                <type>pom</type>
                <scope>import</scope>
            </dependency>
        </dependencies>
    </dependencyManagement> 

After that you need to copy all the dependencies that are needed by your project from pom.xml of spring-base 1.2.5 to the pom.xml of your project.

Also all the used plugins that are defined in pom.xml of spring-base 1.2.5 need to be copied to the pom.xml of your project.
