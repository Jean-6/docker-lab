# Dockerfile

FROM openjdk:17-jdk-slim
LABEL author="Jean Jaures"
WORKDIR /app
COPY target/paris-janitor-ms-user-0.0.1-SNAPSHOT.jar app.jar
EXPOSE 9090
ENTRYPOINT ["java", "-jar","app.jar"]