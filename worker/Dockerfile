FROM salujaji/worker-base:latest AS build
WORKDIR /code
COPY . .
RUN  mvn package -D skipTests

FROM eclipse-temurin:8-jre-alpine AS run
WORKDIR /run
COPY --from=build /code/target/worker-jar-with-dependencies.jar worker.jar
CMD java -jar worker.jar
