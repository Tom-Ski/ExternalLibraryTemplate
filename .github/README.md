# Simple Gradle project structure for cross platform libraries

-----

### Structure

**build.gradle** contains groupId, library name, version and descriptions for the library. It also sets up repositories for the child buildscripts.

**settings.gradle** dictates what child projects you want. By default it is just **core**, but you can have many. An example for this would be platform specific implementations that rely on different platform SDKs.

#### Subprojects

Each subproject needs to declare its artifact ID, as each sub project will be deployed with its own artifact ID. This is handled in the **subproject/build.gradle** file.

Compile dependencies are also declared inside the subproject, by default this goes through the master **dependencies.gradle** script with path **gradle/dependencies.gradle**.
This is for convenience and to keep all versions and dependencies in one place.


## Installing

Run `gradlew install` from command line, this will install to your local maven repository.  

## Using your library

In any gradle project, make sure you have the **mavenLocal()** repository and add the following line for your project dependencies: 

`compile my.custom.package:myArtifactId:version`
