#### Stage 1: Build the application
FROM openjdk:8-jdk-alpine as builder
WORKDIR /app
COPY . /app
RUN ./mvnw clean package -DskipTests -Dhttps.protocols=TLSv1.2

#### Stage 2: A minimal docker image with command to run the app 
FROM openjdk:8-jre-alpine as runtime
COPY --from=builder /app/target/*.jar /app/polling-app-server.jar
EXPOSE 8080
ENTRYPOINT ["java","-Djava.security.egd=file:/dev/./urandom","-jar","/app/polling-app-server.jar"]