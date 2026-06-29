# VProfile Application

VProfile is a Java web application built with Spring MVC and Spring Security for user registration, authentication, profile management, and related web features. The project also includes integrations for MySQL, RabbitMQ, Elasticsearch, and Memcached.

## Features

- User registration and login
- Profile management and account-related workflows
- JSP-based web UI
- File upload support
- Integration with MySQL for persistence
- Messaging and search integrations via RabbitMQ and Elasticsearch
- Docker-based deployment option

## Tech Stack

- Java 17
- Maven
- Spring Framework 6
- Spring Security 6
- Hibernate / JPA
- JSP / JSTL
- MySQL
- Tomcat
- Docker

## Project Structure

- src/main/java - Application source code
- src/main/resources - Configuration files and SQL scripts
- src/main/webapp - JSP views, CSS, JavaScript, and static assets
- src/test/java - Unit and integration tests
- Docker-files - Docker build files

## Prerequisites

Before building or running the application, make sure you have:

- JDK 17 or newer
- Maven 3.9 or newer
- MySQL running and accessible
- Memcached running (if you use the cache integration)
- RabbitMQ running (if you use messaging features)
- Elasticsearch running (if you use search features)

## Configuration

Application settings are defined in:

- src/main/resources/application.properties

Update the database, cache, RabbitMQ, and Elasticsearch settings to match your local environment.

## Build

From the project root, run:

```bash
mvn -DskipTests package
```

This produces a WAR file at:

- target/vprofile-v2.war

The build was verified successfully with Maven and produced the WAR artifact above.

## Run Locally

You can deploy the generated WAR to Tomcat or run it using a servlet container that supports Java web applications.

1. Copy the WAR file to your servlet container's deployment directory.
2. Start the servlet container.
3. Open the application in your browser:

```text
http://localhost:8080/
```

## Docker

A Docker image is also provided for deployment with Tomcat.

Build the image:

```bash
docker build -f Docker-files/app/Dockerfile -t vprofile-app .
```

Run the container:

```bash
docker run -p 8080:8080 vprofile-app
```

## Notes

The project uses hostnames such as `vprodb`, `vprocache01`, and `vpromq01` in the default configuration. For local development, update those values in the properties file to match your environment.

## License

No license file is currently included in the repository.
