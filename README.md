FROM eclipse-temurin:17

WORKDIR /app

COPY target/*.jar app.jar

CMD ["java", "-jar", "app.jar"]

FROM tomcat:9.0

COPY target/*.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 7089

CMD ["catalina.sh","run"]

git clone <github-url>
cd <project-name>
git status

git switch -c <your-name>
git branch
git status

mvn clean
mvn test
mvn install
mvn clean package

java -jar target/<jar-name>.jar

git status
git add .
git commit -m "Completed lab task"
git push -u origin <your-branch>

docker ps -a
docker image ls
docker login

docker build -t myapp .
docker run myapp

docker run -d -p 7089:8080 --name lmcontainer lmsimage
docker tag lmsimage <username>/lmsimage:latest
docker push <username>/lmsimage:latest
docker pull <username>/lmsimage:latest
