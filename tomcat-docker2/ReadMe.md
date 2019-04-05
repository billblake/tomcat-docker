mvn archetype:generate "-DarchetypeGroupId=org.apache.maven.archetypes" "-DarchetypeArtifactId=maven-archetype-webapp" "-DarchetypeVersion=1.4"

mvn clean install
 
docker build -t tomcat-docker2 .

docker run -it --rm -p 8080:8080 -v C:\tmp\tomcat-docker\tomcat-docker2\target\:/usr/local/tomcat/webapps/ --name test2 tomcat-docker2

goto http://localhost:8080/tomcat-docker2/
