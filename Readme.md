# Docker Java Application

A Spring Boot application containerized with Docker and automated CI/CD using Jenkins.

## Project Structure

```
docker-java-app/
├── src/main/java/
│   └── com/levo/dockerexample/
│       ├── DockerApp.java
│       └── controller/
│           └── HelloController.java
├── Dockerfile
├── Jenkinsfile
└── pom.xml
```

## Prerequisites

- JDK 8 or later
- Maven 3.x
- Docker
- Jenkins

## Local Development

1. Build the application:
```bash
mvn clean install
```

2. Build Docker image:
```bash
docker build -t quasarcelestio/example:latest .
```

3. Run the container:
```bash
docker run -p 8080:8080 quasarcelestio/example:latest
```

## Jenkins Pipeline

The project includes a Jenkins pipeline that:
- Clones the repository
- Builds with Maven
- Creates Docker image
- Pushes to Docker Hub

### Jenkins Configuration Required:

1. Tools:
   - JDK: OpenJDK9
   - Maven: jenkins-maven

2. Credentials:
   - Docker Hub credentials (ID: dockerhubcred)

## API Endpoints

- GET `/`: Returns Hello World message

## Docker Hub

The Docker image is available at:
`quasarcelestio/example:latest`

// ...existing code...

## Screenshots

### ScreenShots
![Jenkins Pipeline](screenshots/jenkins-pipeline.png)

![Docker Build](screenshots/docker-build.png)

![Application](screenshots/app-running.png)

![Jenkins Tools](screenshots/jenkins-tools.png)
