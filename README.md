# stayConnected

## Project 
The goal is to set a service displaying a list of countries using Java 11 & Springboot.  
Data must be available both with A REST Api and a Front-end application.

## Set-up
The model country is made of a name and a country code (2 capital letters).  
Data are stored locally in a MySql database.  
Connection to the Database is set in project/src/resources/applications.properties.

## Build
The app has been built using successively :  
- ./mvnw clean package  
- java -jar target/stayConnected-0.0.1-SNAPSHOT.jar

## Consuming the .JAR
Once the Java Archive has been made, the following java command (referencing to the virtual machine installed) is a way to run the program :  
- java -jar ~/stayConnected-0.0.1-SNAPSHOT.jar

## Front-end
Consists of several forms accessing the different endpoints of the API.

## Curl commands
- GET /countries => La liste de tous les pays  
> curl 'localhost:8080/countries'  
- GET /country/{id} => Les informations du pays portant cet id  
> curl 'localhost:8080/country/18'  
- POST /country => Enregistre un pays  
> curl -X POST -d 'name=America' -d 'code=AM' http://localhost:8080/country  
- PUT /country/{id} => Met à jour un pays portant cet id  
> curl -X PUT -H "Content-Type: application/json" -d '{"name":"Quatar", "code":"QA"}' http://localhost:8080/country/18  
- DELETE /country/{id} => Supprime le pays portant cet id  
> curl -X DELETE http://localhost:8080/country/18  
