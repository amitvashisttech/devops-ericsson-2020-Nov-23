# Build an Springboot Petclinic App with Maven. 

## Step 1: Change the Dir. 
```
cd 05-App-Code/petclinic-code
```

## Step 2: Install Java & Maven
```
apt-get install default-jdk -y 
apt-get install maven -y 
mvn -version
```

## Step 3: Maven Clean
```
mvn clean
```

## Step 4: Maven Compile
```
mvn compile
```

## Step 4: Maven Test
```
mvn test
```

## Step 5: Maven Package
```
mvn package
ls -ltr target/*.war
```





# Let's Deploy Petclinic via docker based Tomcat

## Step 1: Switch the Dir to Dockerfile
```
cd ../../03-Dockerfile/
mkdir tomcat
cd tomcat
``` 

## Step 2: Create a Dockerfile like below:
```
cat Dockerfile
FROM tomcat:8.0

COPY petclinic.war /usr/local/tomcat/webapps/

```

## Step 3: Now Copy Petclinic WAR Package here:
```
cp -rf ../../05-App-Code/petclinic-code/target/petclinic.war . 
ls -ltr
```

## Step 4: Build a new Tocmat Petcline Image & Run the container.
```
docker build -t testtomcat:v1 .
docker images
docker ps
docker run -d -p 8081:8080 testtomcat:v1
```

## Now you can check the app in web browser. http://172.31.0.100:8081/petclinic


