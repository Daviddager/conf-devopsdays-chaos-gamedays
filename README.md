# Toolbox with resources to prepare and run a Chaos Gamedays

<div align="center">
  <img src="https://github.com/yurynino/conf-devopsdays-chaos-gamedays/blob/master/images/gamedays_animation.gif" width="400px" />

  [![java](https://img.shields.io/badge/java-v1.8-green.svg)](https://www.oracle.com/java/technologies)
  [![spring-boot](https://img.shields.io/badge/springboot-v2.2.1-red.svg)](https://www.javatpoint.com/spring-boot-version)
  [![mysql](https://img.shields.io/badge/mysql-v5.7-blue.svg)](https://dev.mysql.com)
  [![gradle](https://img.shields.io/badge/gradle-v5.5.X-yellow.svg)](https://gradle.org/install/)
  [![maven](https://img.shields.io/badge/maven-v3.6.X-red.svg)](https://maven.apache.org/)
  [![chaos-monkey](https://img.shields.io/badge/chaosmonkey-v2.0.0-yellow.svg)](https://codecentric.github.io/chaos-monkey-spring-boot/2.0.0/)
  [![datadog](https://img.shields.io/badge/datadog-v7.x-red.svg)](https://www.datadoghq.com/)
  [![gatling](https://img.shields.io/badge/python-v3.7.X-green.svg)](https://www.python.org/)
</div>

  > This repository contains the artifacts required to run a chaos gameday in a sample cluster with spring boot microservices. Please take a look at the architecture.

<div align="center">
    <img src="https://github.com/yurynino/conf-devopsdays-chaos-gamedays/blob/master/images/microservices_gameday.png" width="600px" />
</div>

## Table of Contents

- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Quickstart](#quickstart)
- [Contributing](#contributing)
- [Further Reading / Useful Links](#further-reading--useful-links)

## Prerequisites

You will need the following things properly installed on your computer:

* [Java 1.8](https://www.oracle.com/java/technologies/javase-jdk8-downloads.html)
* [Maven 3.6.x](https://maven.apache.org/download.cgi)
* [Mysql 5.7.x](https://dev.mysql.com/downloads/mysql/5.7.html)

## Installation

1. Clone this repository.
```git
git clone https://github.com/yurynino/chaos-gameday-toolbox.git
```

2. Replace the URL and credentials to access the database.

3. Run the maven commands to clean and install in each microservice.
```maven
cd discovery-service
mvn clean install

cd order-service
mvn clean install

cd customer-service
mvn clean install

cd product-service
mvn clean install

cd gateway-service
mvn clean install
```

4. Run the commands to start the microservices.
```bash
$ java -jar target/discovery-service-1.0-SNAPSHOT.jar

$ java -jar target/order-service-1.0-SNAPSHOT.jar --spring.profiles.active=chaos-monkey
$ java -jar -Dserver.port=9091 target/order-service-1.0-SNAPSHOT.jar --spring.profiles.active=chaos-monkey

$ java -jar target/product-service-1.0-SNAPSHOT.jar --spring.profiles.active=chaos-monkey
$ java -jar -Dserver.port=9092 target/product-service-1.0-SNAPSHOT.jar --spring.profiles.active=chaos-monkey

$ java -jar target/customer-service-1.0-SNAPSHOT.jar --spring.profiles.active=chaos-monkey
$ java -jar -Dserver.port=9093 target/customer-service-1.0-SNAPSHOT.jar --spring.profiles.active=chaos-monkey
```


-----------
## Contributing
See [CONTRIBUTING.md](https://github.com/yurynino/conf-devopsdays-chaos-gamedays/blob/master/CONTRIBUTING.md)
