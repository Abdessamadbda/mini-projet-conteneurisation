FROM openjdk:17-jre-slim
ENV SPRING_PROFILES_ACTIVE=production
WORKDIR /app
COPY ["target/spring-boot-data-jpa-mysql.jar", "./"]
EXPOSE 8080
CMD ["java", "-jar", "spring-boot-data-jpa-mysql.jar"]