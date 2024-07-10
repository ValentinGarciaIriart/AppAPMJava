# Use the base image with OpenJDK 11 JRE slim version
FROM openjdk:11.0.2-jre-slim

# Set the working directory inside the container
WORKDIR /app

# Copy the application JAR into the container at /app directory
COPY target/microservice-kubernetes-demo-customer-0.0.1-SNAPSHOT.jar /app/

# Specify the command to run your application using java
CMD ["java", "-Xmx400m", "-Xms400m", "-jar", "microservice-kubernetes-demo-customer-0.0.1-SNAPSHOT.jar"]

# Document that the container listens on port 8080
EXPOSE 8080
