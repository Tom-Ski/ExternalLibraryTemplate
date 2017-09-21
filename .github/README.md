# Simple Gradle project structure for cross platform libraries

-----

### Structure

build.gradle contains groupId, library name, version and descriptions for the library. It also sets up repositories for the child buildscripts.

settings.gradle dictates what child projects you want. By default it is just core, but you can have many. A use for this would be platform specific implementations.

#### Sub projects

Each sub project needs to declare its artifact ID, as each sub project will be deployed with its own artifact id. This is handled in the subproject/build.gradle file.

Compile dependencies are also declared inside the subproject, by default this goes through the master dependencies.gradle script with path gradle/dependencies.gradle.
This is for convenience and to keep all versions and dependencies in one place.


## Installing

Run `gradlew install` from command line, this will install to your local maven repository.  

This will allow you to use the following:
`compile my.custom.package:myArtifactId:version' 

in your projects to depend on each sub project of this project.
