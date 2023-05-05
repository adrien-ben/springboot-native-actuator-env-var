# springboot-native-actuator-env-var

Example showing that actuator's port cannot be set at runtime via env variables.

## Build and run native image 

```shell
mvn -Pnative spring-boot:build-image

docker run -p 8080:8080 -p 8082:8082 -e MANAGEMENT_SERVER_PORT=8082 --rm actuator-env-var:0.0.1-SNAPSHOT
```
## Solution

This is the expected behavior. See https://github.com/spring-projects/spring-boot/issues/35288.
As a workaround setting a default value for `management.server.port` in the properties file then overriding it with the environment variable works.

