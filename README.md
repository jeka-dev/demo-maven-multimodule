# Demo Maven Multi-Module with Jeka

This demo shows how to install a Maven-built Java application from source code using Jeka.

This example uses a Maven multi-module project. Users can install it on their computer as either a JVM application or a native executable.

## Install the Application

Install as a JVM application:

```shell
jeka app: install repo=https://github.com/jeka-dev/demo-maven-multimodule
```

Install as a native application:

```shell
jeka app: install repo=https://github.com/jeka-dev/demo-maven-multimodule runtime=NATIVE
```

Run the application:
```shell
demo-maven-multimodule
```

## How It Works

Just add the [jeka.properties](./jeka.properties) file to your project.
This file tells Jeka which JDK to use and the build commands to run.

### Project Structure

- **app**: Main application module
- **share**: Shared library module

### Requirements

To make this work, you need:

1. **Fat JAR support**: The [app/pom.xml](./app/pom.xml) uses the *maven-shade-plugin* to create a fat JAR for JVM mode
2. **Native image support**: The [app/pom.xml](./app/pom.xml) includes the *native-maven-plugin* to build native executables
3. **Maven wrapper**: Included so the app can build on any computer, even without Maven installed



