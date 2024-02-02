FROM maven:3.9-eclipse-temurin-8 AS builder

WORKDIR /app

COPY . .

RUN mvn clean package -DskipTests

FROM eclipse-temurin:8-jre

WORKDIR /app

COPY --from=builder /app/target/*.jar examPolytech2024.jar

EXPOSE 8448

LABEL maintainer="Raphael"

CMD ["java","-jar","examPolytech2024.jar"]