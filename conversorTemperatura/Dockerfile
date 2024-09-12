# Etapa de build
FROM maven:3.8.2-jdk-11 AS build
COPY . .
RUN mvn clean package -DskipTests

# Etapa de runtime
FROM openjdk:11-jdk-slim
COPY --from=build /app/target/conversorTemperatura-0.0.1-SNAPSHOT.jar conversorTemperatura.jar
EXPOSE 8080
ENTRYPOINT ["java", "-jar", "conversorTemperatura.jar"]
