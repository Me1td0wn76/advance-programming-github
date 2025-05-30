# ビルド用イメージ
FROM maven:3.9.6-eclipse-temurin-17 AS build
WORKDIR /app
COPY . .
RUN chmod +x mvnw
RUN ./mvnw clean package -DskipTests

# 実行用イメージ
FROM eclipse-temurin:17
WORKDIR /app
COPY --from=build /app .
RUN chmod +x mvnw
EXPOSE 8080
ENTRYPOINT ["./mvnw", "spring-boot:run"]
