# Use openjdk 8  image as the base image
FROM maven:3.8.3-jdk-8 AS build
RUN mkdir -p /app
WORKDIR /app
COPY pom.xml /app
COPY src /app/src
RUN mvn clean compile assembly:single

#FROM openjdk:8-alpine
#COPY --from=build /app/target/*.jar SimpleHttpServer-1.0-SNAPSHOT.jar
#COPY . .
#EXPOSE 8000
#ENTRYPOINT ["java","-jar","SimpleHttpServer-1.0-SNAPSHOT.jar"]
#CMD ["java","ServerTest.java"]
#CMD java -classpath src/java com.simplehttpserver.httpserver.ServerTest

FROM openjdk:8
COPY httpserver.db httpserver.db
ADD target/SimpleHttpServer-1.0-SNAPSHOT-jar-with-dependencies.jar SimpleHttpServer-1.0-SNAPSHOT-jar-with-dependencies.jar

ENTRYPOINT ["java", "-jar","SimpleHttpServer-1.0-SNAPSHOT-jar-with-dependencies.jar"]
EXPOSE 8000