# Clone the required git repositories
FROM alpine/git as clone
WORKDIR /app
RUN git clone https://github.com/WaCoDiS/metadata-connector.git metadata-connector 

# Build metadata-connector
FROM maven:3.5-jdk-8-alpine as build 
WORKDIR /app
COPY --from=clone /app/metadata-connector  /app/metadata-connector 
RUN mvn -f ./metadata-connector/pom.xml clean install

# Run metadata-connector
FROM openjdk:alpine
WORKDIR /app

COPY --from=build app/metadata-connector/metadata-connector-app/target/metadata-connector-app-0.0.1-SNAPSHOT.jar /app/metadata-connector-app.jar
CMD ["java", "-jar", "/app/metadata-connector-app.jar"]