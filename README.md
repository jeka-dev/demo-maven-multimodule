# Demo Maven Multi-Module with Jeka

This demo shows how to install a Maven-built Java application from source code using Jeka.

This example uses a Maven multi-module project. Users can install it on their computer as either a JVM application or a native executable.

## Prerequisites

[JeKa installed](https://jeka-dev.github.io/jeka/installation/). JeKa downloads the JDK (GraalVM, as set in
[jeka.properties](./jeka.properties)) and Maven runs through its wrapper: you don't need Maven or a JDK.

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

Uninstall it:
```shell
jeka app: uninstall name=demo-maven-multimodule
```

## How It Works

Just add the [jeka.properties](./jeka.properties) file to your project.
This file tells JeKa which JDK to use, and the build commands to run: `jeka.program.build` for the JVM application,
`jeka.program.build.native` for the native one. Both call `maven: wrapPackage` on the `app` module.

### Project Structure

- **app**: Main application module
- **share**: Shared library module

### Requirements

To make this work, you need:

1. **Fat JAR support**: The [app/pom.xml](./app/pom.xml) uses the *maven-shade-plugin* to create a fat JAR for JVM mode
2. **Native image support**: The [app/pom.xml](./app/pom.xml) includes the *native-maven-plugin* to build native executables
3. **Maven wrapper**: Included so the app can build on any computer, even without Maven installed

## Links

- [app KBean](https://jeka-dev.github.io/jeka/reference/kbeans-app/)
- [maven KBean](https://jeka-dev.github.io/jeka/reference/kbeans-maven/)
