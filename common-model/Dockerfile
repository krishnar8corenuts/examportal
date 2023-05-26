#FROM eclipse-temurin:17-jdk-alpine
#VOLUME /tmp
#ARG JAR_FILE=target/*.jar
#COPY ${JAR_FILE} common-model
#ENTRYPOINT ["sh", "-c", "java ${JAVA_OPTS} -jar /common-model.jar"]


# For Java 8, try this
# FROM openjdk:8-jdk-alpine

# For Java 11, try this
FROM adoptopenjdk/openjdk11:alpine-jre

# Refer to Maven build -> finalName
ARG JAR_FILE= /home/mohs/.m2/repository/com/feuji/common-model/0.0.1/common-model-0.0.1.jar

# cd /opt/app
WORKDIR /opt/app

# cp target/spring-boot-web.jar /opt/app/app.jar
ADD ${JAR_FILE} common-model.jar

# java -jar /opt/app/app.jar
ENTRYPOINT ["java","-jar","common-model.jar"]
