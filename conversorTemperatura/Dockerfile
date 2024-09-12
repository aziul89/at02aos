# Etapa de build
FROM maven:3.8.2-jdk-11 AS build
WORKDIR /app
COPY . /app
RUN mvn clean package -DskipTests

# Etapa de runtime
FROM openjdk:11-jdk-slim
WORKDIR /app
COPY --from=build /app/target/conversorTemperatura-0.0.1-SNAPSHOT.jar app.jar
EXPOSE 8080
ENTRYPOINT ["java", "-jar", "app.jar"]
