# Step 1

# Use Java image
FROM openjdk:17-jdk-slim

# Define workspace into container
WORKDIR /app

# Copy generated JAR file by Maven
COPY target/*.jar app.jar

# Expose the port of the Spring Boot application (default 8081)
EXPOSE 8081

# Launch app
CMD ["java","-jar","app.jar"]