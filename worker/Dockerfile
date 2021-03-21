FROM maven:3.5-jdk-8-alpine AS builder

LABEL maintainer="EPITECH TOULOUSE -> Anthony DENIN -> PROMO 2024"

WORKDIR /app

COPY . /app

RUN mvn dependency:resolve

RUN mvn package


FROM openjdk:8-jre-alpine

LABEL maintainer="EPITECH TOULOUSE -> Anthony DENIN -> PROMO 2024"

EXPOSE 80

COPY --from=builder /app/target/worker-jar-with-dependencies.jar .

CMD ["java", "-jar", "worker-jar-with-dependencies.jar"]
