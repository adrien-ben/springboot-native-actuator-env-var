# springboot-native-actuator-env-var

Example showing that actuator's port cannot be set at runtime via env variables.

## Build and run native image 

```shell
mvn -Pnative spring-boot:build-image

docker run -p 8080:8080 -p 8081:8081 -e SPRING_PROFILES_ACTIVE=dev -e MANAGEMENT_SERVER_PORT=8081 --rm actuator-env-var:0.0.1-SNAPSHOT
```
