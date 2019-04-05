mvn archetype:generate "-DarchetypeGroupId=org.apache.maven.archetypes" "-DarchetypeArtifactId=maven-archetype-webapp" "-DarchetypeVersion=1.4"

mvn clean install
 
docker build -t tomcat-docker1 .

docker run -it --rm -p 80:8080 --name hello tomcat-docker1

goto http://localhost/tomcat-docker1/