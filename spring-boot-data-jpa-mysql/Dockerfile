#Pahse 1
FROM maven AS build
WORKDIR /app/myapp
COPY . .
RUN mvn clean package -DskipTests

#Phase 2
FROM openjdk:17-alpine
WORKDIR /app
EXPOSE 8080
COPY --from=build /app/myapp/target/spring-boot-data-jpa*.jar app.jar
CMD ["java","-jar","app.jar"]