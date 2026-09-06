FROM eclipse-temurin:17

WORKDIR /app

COPY target/*.jar app.jar

CMD ["java", "-jar", "app.jar"]

FROM tomcat:9.0

COPY target/*.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 7089

CMD ["catalina.sh","run"]
