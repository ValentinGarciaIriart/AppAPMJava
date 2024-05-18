FROM openjdk:11.0.2-jre-slim

# Set the working directory
WORKDIR /app

# Copy the application JAR
COPY target/microservice-kubernetes-demo-order-0.0.1-SNAPSHOT.jar /app/

# Copy the APM agent from one level up
COPY elastic-apm-agent-1.49.0.jar /app/elastic-apm-agent.jar

# Configuration and start command including the APM agent
CMD ["/usr/bin/java", "-Xmx400m", "-Xms400m", \
  "-javaagent:/app/elastic-apm-agent.jar", \
  "-Delastic.apm.service_name=Order", \
  "-Delastic.apm.secret_token=b3hCoIk2pNQPDeVOaG", \
  "-Delastic.apm.server_url=https://ae27d0448acf4a66b82af11e5ae6d215.apm.eastus2.azure.elastic-cloud.com:443", \
  "-Delastic.apm.environment=my-environment", \
  "-Delastic.apm.application_packages=org.example", \
  "-jar", "/app/microservice-kubernetes-demo-order-0.0.1-SNAPSHOT.jar"]

# Expose the port the application runs on
EXPOSE 8080
