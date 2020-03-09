# Spring Boot 2 demo of Resilience4j

Based on the sample from https://github.com/resilience4j/resilience4j-spring-boot2-demo

This demo shows how to use the fault tolerance library [Resilience4j](https://github.com/resilience4j/resilience4j) in a Spring Boot 2 application.

See [User Guide](https://resilience4j.readme.io/docs/getting-started-3) for more details.

The [BackendAService](https://github.com/resilience4j/resilience4j-spring-boot2-demo/blob/master/src/main/java/io/github/robwin/service/BackendAService.java) shows how to use the Resilience4j Annotations.


The [BackendBController](https://github.com/resilience4j/resilience4j-spring-boot2-demo/blob/master/src/main/java/io/github/robwin/controller/BackendBController.java) shows how to use the functional style and the Spring Reactor operators.


## Getting Started

Just run the Application.java in your IDE.  
Application is running on http://localhost:9080.

## Monitoring with Prometheus and Grafana (OPTIONAL)

### Requirements
[Docker](https://docs.docker.com/install/) and [Docker Compose](https://docs.docker.com/compose/install/) installed.
 
### Step 1
Use docker-compose to start Grafana and Prometheus servers.
- In the root folder
```sh
docker-compose -f docker-compose.yml up
```
### Step 2
Check the Prometheus server.
- Open http://localhost:9090
- Access status -> Targets, both endpoints must be "UP"

### Step 3
Configure the Grafana.
- Open http://localhost:3000
- **Configure integration with Prometheus**
    - Access configuration
    - Add data source
    - Select Prometheus
    - Use url "http://localhost:9090" and access with value "Browser"
- **Configure dashboard**
    - Access "home"
    - Import dashboard
    - Upload dashboard.json from /docker

## Further links
https://medium.com/capital-one-tech/resiliency-patterns-at-the-edge-capital-one-a5b4d41d477e
https://www.slideshare.net/ufried/patterns-of-resilience
https://docs.microsoft.com/en-us/azure/architecture/patterns/bulkhead