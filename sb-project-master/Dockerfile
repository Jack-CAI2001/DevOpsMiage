FROM docker-registry.default.svc:5000/saberkan-tmp/openjdk:8-jdk-alpine

COPY target/gs-rest-service-0.1.0.jar  app.jar

EXPOSE 8080
ENTRYPOINT ["java","-jar","/app.jar"]
