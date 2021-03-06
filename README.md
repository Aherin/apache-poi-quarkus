# apache-poi-quarkus project

This project uses Quarkus, the Supersonic Subatomic Java Framework.

If you want to learn more about Quarkus, please visit its website: https://quarkus.io/ .


#Windows 

### Native build
In case of developing on Windows native image has to be built in Docker:
 
 ```shell script
 docker build -f src/main/docker/Dockerfile.jvm -t quarkus/apache-poi-quarkus-jvm .
 docker run -i --rm -p 8080:8080 quarkus/apache-poi-quarkus-jvm
```

In case of developing on Windows native image has to be built in Docker:
### Inspection build
 ```shell script
 docker build  -f inspection.Dockerfile -t apache-poi-inspection . 
 docker run -p 8080:8080 -v c:/data:/data -t apache-poi-inspection
```

## Running the application in dev mode

You can run your application in dev mode that enables live coding using:
```
./mvnw quarkus:dev
```

#Linux  

## Packaging and running the application

The application can be packaged using `./mvnw package`.
It produces the `apache-poi-quarkus-1.0.0-SNAPSHOT-runner.jar` file in the `/target` directory.
Be aware that it’s not an _über-jar_ as the dependencies are copied into the `target/lib` directory.

The application is now runnable using `java -jar target/apache-poi-quarkus-1.0.0-SNAPSHOT-runner.jar`.

You can create a native executable using: `./mvnw package -Pnative`.

Or, if you don't have GraalVM installed, you can run the native executable build in a container using: `./mvnw package -Pnative -Dquarkus.native.container-build=true`.

You can then execute your native executable with: `./target/apache-poi-quarkus-1.0.0-SNAPSHOT-runner`

If you want to learn more about building native executables, please consult https://quarkus.io/guides/building-native-image-guide.