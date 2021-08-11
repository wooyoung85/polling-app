FROM openjdk:8-jre-alpine
COPY target/*.jar /app/polling-app-server.jar
EXPOSE 8080
ENTRYPOINT ["java","-Djava.security.egd=file:/dev/./urandom","-jar","/app/polling-app-server.jar"]