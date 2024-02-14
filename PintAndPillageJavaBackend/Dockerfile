# Gebruik een OpenJDK image als basis
FROM maven:3.9.6-amazoncorretto-17 AS builder

# Zet de werkdirectory in
WORKDIR /app

# Kopieer de broncode naar de werkdirectory
COPY . .

# Installeer de afhankelijkheden en bouw de Spring Boot applicatie met Maven
RUN mvn clean package -DskipTests

# Definieer de uiteindelijke image
FROM openjdk:17-jdk-slim

# Zet de werkdirectory in
WORKDIR /app

# Kopieer het JAR-bestand van de gebouwde Spring Boot applicatie naar de image
COPY --from=builder /app/target/*.jar app.jar

# Start de Spring Boot applicatie
ENTRYPOINT ["java", "-jar", "app.jar"]