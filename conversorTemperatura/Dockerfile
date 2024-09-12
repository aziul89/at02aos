# Etapa de Build
FROM maven:3.8.2-jdk-11 AS build
WORKDIR /app
COPY . /app
RUN mvn clean package -DskipTests

# Etapa de Runtime
FROM openjdk:11-jdk-slim
WORKDIR /app
COPY --from=build /app/target/conversorTemperatura-0.0.1-SNAPSHOT.jar conversorTemperatura.jar
EXPOSE 8080
ENTRYPOINT ["java", "-jar", "conversorTemperatura.jar"]
