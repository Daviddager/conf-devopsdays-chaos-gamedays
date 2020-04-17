# 2 EXPERIMENT with Chaos Monkey for Spring Boot

  [![chaos-monkey](https://img.shields.io/badge/chaosmonkey-v2.0.0-yellow.svg)](https://codecentric.github.io/chaos-monkey-spring-boot/2.0.0/)
  [![java](https://img.shields.io/badge/java-v1.8-green.svg)](https://www.oracle.com/java/technologies)
  [![maven](https://img.shields.io/badge/maven-v3.6.X-red.svg)](https://maven.apache.org/)
  [![spring-boot](https://img.shields.io/badge/springboot-v2.2.1-red.svg)](https://www.javatpoint.com/spring-boot-version)
  [![mysql](https://img.shields.io/badge/mysql-v5.7-blue.svg)](https://dev.mysql.com)
  [![datadog](https://img.shields.io/badge/datadog-v7.x-red.svg)](https://www.datadoghq.com/)

  > Design an experiment requires the definition of these data: the application name, the bservability tool, a hypothesis, the attack type, duration time, environment and the blast radious. In this case I have just included the code and the instructions to run an experiment with Chaos SpringBoot. However you can find more information about how to create an experiment in the [Further Reading](https://github.com/yurynino/conf-devopsdays-chaos-gamedays/tree/master/2_experiment#furher-reading) section.

<div align="center">
    <img src="https://github.com/yurynino/conf-devopsdays-chaos-gamedays/blob/master/images/gameday_architecture.png" width="600px" />
</div>


## Table of Contents

- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Deployment](#quickstart)
- [Further Reading](#further-reading)


## Prerequisites

You will need the following things properly installed on your computer:

* [Java 1.8](https://www.oracle.com/java/technologies/javase-jdk8-downloads.html)
* [Maven 3.6.x](https://maven.apache.org/download.cgi)
* [Mysql 5.7.x](https://dev.mysql.com/downloads/mysql/5.7.html)


## Installation

1. Clone this repository.
```git
   git clone https://github.com/yurynino/conf-devopsdays-chaos-gamedays
```

2. Replace the URL and credentials to access the database.

3. Run the maven commands to clean and install in each microservice.
```maven
   cd 3_run/discovery-service
   mvn clean install

   cd 3_run/order-service
   mvn clean install

   cd 3_run/customer-service
   mvn clean install

   cd 3_run/product-service
   mvn clean install

   cd  3_run/gateway-service
   mvn clean install
```

4. Run the commands to start the microservices.
```bash
   cd ..

   $ java -jar discovery-service/target/discovery-service-1.0-SNAPSHOT.jar
   $ java -jar order-service/target/order-service-1.0-SNAPSHOT.jar --spring.profiles.active=chaos-monkey
   $ java -jar product-service/target/product-service-1.0-SNAPSHOT.jar --spring.profiles.active=chaos-monkey
   $ java -jar customer-service/target/customer-service-1.0-SNAPSHOT.jar --spring.profiles.active=chaos-monkey
   $ java -jar gateway_service_service/target/gateway-service-1.0-SNAPSHOT.jar
```

## Furher Reading
 - [Documents for Sample Chaos Monkey for Spring Boot](https://piotrminkowski.com/2018/05/23/chaos-monkey-for-spring-boot-microservices/)
 - [Code for Sample Chaos Monkey for Spring Boot](https://github.com/piomin/sample-spring-chaosmonkey)
 - [Documents for Chaos Monkey for Spring Boot](https://codecentric.github.io/chaos-monkey-spring-boot/)
 - [Reference for Chaos Monkey for Spring Boot](https://codecentric.github.io/chaos-monkey-spring-boot/2.2.0/)