FROM maven:3.6.1-jdk-8-alpine AS MAVEN_BUILD

COPY ./ ./

RUN mvn clean package

FROM openjdk:20-slim

COPY --from=MAVEN_BUILD /target/spring-boot-0.0.1-SNAPSHOT.jar /demo.jar

CMD ["java", "-jar", "/demo.jar"]