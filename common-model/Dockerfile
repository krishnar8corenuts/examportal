#FROM eclipse-temurin:17-jdk-alpine
#VOLUME /tmp
#ARG JAR_FILE=target/*.jar
#COPY ${JAR_FILE} common-model
#ENTRYPOINT ["sh", "-c", "java ${JAVA_OPTS} -jar /common-model.jar"]



# Docker Build Maven Stage
FROM maven:3-jdk-8-alpine AS build
# Copy folder in docker
WORKDIR /opt/app
COPY ./ /opt/app
RUN mvn clean install -DskipTests
# Run spring boot in Docker
FROM openjdk:8-jdk-alpine
COPY --from=build /opt/app/target/*.jar common-model.jar
ENV PORT 8081
EXPOSE $PORT
ENTRYPOINT ["java","-jar","/common-model.jar"]
