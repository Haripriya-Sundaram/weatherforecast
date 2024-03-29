# Weather Forecast App

Provide a website which will return the current weather data for a city selected by the user, it should support _London_ and _Hong Kong_.
To fetch the weather data this app will use **OpenWeatherMap.org** API service.

## Overview

The site will display:
* Today's date
* City name
* Overall description of weather (i.e.: "Light rain", "Clear sky", etc)
* Temperature in Fahrenheit and Celsius
* Sunrise and sunset times in 12 hour format (i.e.: 7:35am; 7:23pm)



## Implementation

### Work plan
1. Create the base project files with Maven configuration and a simple Spring Boot app exposing a Welcome page
2. Add a Rest Controller that will return the weather data for a given city 
3. Create an OpenWeatherMap API client and connect it to the Weather controller. It will require logic to map the response from OWM to the Weather view object.
4. Add caching to reduce the calls to OWM service, there are recommendations about the data update frequency.
5. The Forecast app will provide a regular HTML page return to render the Weather data and also a REST kind endpoint to get the data in JSON format.

### Configurations

#### Maven 3
To make sure this project can be built with Maven 3.3, I setup the Maven Wrapper tool to use Maven 3.3.9 (latest 3.3 release)

The command to do that is
```
>$ mvn -N io.takari:maven:wrapper -Dmaven=3.3.9
```
Ref to tool: https://github.com/takari/maven-wrapper

#### Java 8
To build and run this project, Java 8 is required.

Most of the current Operating System distributions have the Java JRE installed already.

Download it from the [Official Java 8 site](http://www.oracle.com/technetwork/java/javase/downloads/jre8-downloads-2133155.html)

### Deploy and run

When started, the App will run by default with an embedded Tomcat server on port 8080.
i.e. to access the app in your local environment, start the app and in your browser go to
```
http://localhost:8080
```

**Development**

From the project's root dir:
```
>$ ./mvnw spring-boot:run
```

**Production**

_Build_
```
>$ ./mvnw package
```
this will generate an _api-0.0.1-SNAPSHOT.jar_ file in the ./target directory

_Run_

The packaged jar file can be copied to another directory or simply run from there with the following command
```
>$ java -jar target/api-0.0.1-SNAPSHOT.jar
```

## Links

* OpenWeatherMap.org - https://openweathermap.org 
* About Kelvin degrees -  https://en.wikipedia.org/wiki/Kelvin
* Epoch, Unix time - https://en.wikipedia.org/wiki/Unix_time
* Spring Boot Caching - https://docs.spring.io/spring-boot/docs/current/reference/html/boot-features-caching.html
* Caffeine cache - https://github.com/ben-manes/caffeine

## Versions and changes
This project follows [Keep a Changelog](https://keepachangelog.com) and [Semantic Versioning](https://semver.org)
