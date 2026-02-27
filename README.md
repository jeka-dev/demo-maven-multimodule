# Demo Maven Multi-Module with Jeka

This demo showcases how to execute Maven builds from source using Jeka.

## Project Structure

This project demonstrates how to handle multi-module Maven projects with Jeka. The project structure is organized as follows:

- **app**: Main application module with fat JAR and native image configuration
- **share**: Shared library module used by the app

## Setup

### JVM build 

Creates a fat JAR using maven-shade-plugin (see `app/pom.xml`)


- **Native image builds**: Compiles to native executable using GraalVM native-maven-plugin (see `app/pom.xml` native profile)



## Setup

We use Jeka to render this application directly installable on any computer just from 

Build instructions are configured in `jeka.properties`, where Jeka delegates to Maven with proper environment setup (PATH, JAVA_HOME, GRAALVM_HOME).





## Requirements

- Java 25
- GraalVM (for native image builds)
- Maven 3.x
- Jeka 0.11.x
