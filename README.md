# In My VDI


Open 'x64 Native tool'
setx -m JAVA_HOME "C:\Software\jdk-16.0.2"
OR
setx -m JAVA_HOME "C:\Software\graalvm-ce-java16-21.2.0"

navigate to below path and execute
C:\experiments\hello>..\..\Software\apache-maven-3.8.1\bin\mvn clean package -Pnative -DskipTests

this will generate a native image ie an exe. which can be up in no time.

# In My VDI with Docker
add  below property to application.properties
quarkus.native.container-build=true
and execute 

../../Software/apache-maven-3.8.1/bin/mvn package -Pnative

OR 
directly execute
../../Software/apache-maven-3.8.1/bin/mvn package -Pnative -Dquarkus.native.container-build=true




# hello Project

This project uses Quarkus, the Supersonic Subatomic Java Framework.

If you want to learn more about Quarkus, please visit its website: https://quarkus.io/ .

## Running the application in dev mode

You can run your application in dev mode that enables live coding using:
```shell script
./mvnw compile quarkus:dev
```

> **_NOTE:_**  Quarkus now ships with a Dev UI, which is available in dev mode only at http://localhost:8080/q/dev/.

## Packaging and running the application

The application can be packaged using:
```shell script
./mvnw package
```
It produces the `quarkus-run.jar` file in the `target/quarkus-app/` directory.
Be aware that it’s not an _über-jar_ as the dependencies are copied into the `target/quarkus-app/lib/` directory.

If you want to build an _über-jar_, execute the following command:
```shell script
./mvnw package -Dquarkus.package.type=uber-jar
```

The application is now runnable using `java -jar target/quarkus-app/quarkus-run.jar`.

## Creating a native executable

You can create a native executable using: 
```shell script
./mvnw package -Pnative
```

Or, if you don't have GraalVM installed, you can run the native executable build in a container using: 
```shell script
./mvnw package -Pnative -Dquarkus.native.container-build=true
```

You can then execute your native executable with: `./target/hello-1.0.0-SNAPSHOT-runner`

If you want to learn more about building native executables, please consult https://quarkus.io/guides/maven-tooling.html.

## Related Guides

- RESTEasy JAX-RS ([guide](https://quarkus.io/guides/rest-json)): REST endpoint framework implementing JAX-RS and more

## Provided Code

### RESTEasy JAX-RS

Easily start your RESTful Web Services

[Related guide section...](https://quarkus.io/guides/getting-started#the-jax-rs-resources)
