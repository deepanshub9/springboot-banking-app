#-------STAGE 1 ----------


#Pull base images
FROM maven:3.8.3-openjdk-17 AS builder


#Working directory
WORKDIR  /app

#Copy code
COPY . /app

#Generate jar files
RUN mvn clean install -DskipTests=true



#-------STAGE 2 ----------------



FROM openjdk:17-alpine

WORKDIR /app

COPY --from=builder /app/target/*.jar /app/target/bankapp.jar

#Expose the port
EXPOSE 8080

#Execute the JAR files using java command and -jar file
ENTRYPOINT ["java", "-jar", "/app/target/bankapp.jar"] 


