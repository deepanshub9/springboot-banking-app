# Banking Application

## Overview

This is a Spring Boot-based banking application designed to provide secure and efficient banking functionalities. The project uses Maven for dependency management and generates a JAR file for deployment. The backend is powered by MySQL as the relational database.

## Deployment Architecture

The application is deployed on an AWS EC2 instance and containerized using Docker. A `docker-compose.yml` file is included for easy setup and management of services.

## Features

- **Spring Boot**: Backend API implementation.
- **Maven**: Dependency and build management.
- **MySQL**: Database management system.
- **Docker**: Containerization for portability and scalability.
- **Docker Compose**: Simplifies multi-container deployments.
- **AWS EC2**: Cloud hosting environment.
- **Advanced Docker Concepts Implemented**:
  - Image size compression
  - Multi-stage builds
  - Networking between containers
  - Image creation and registry storage
  - Volume persistence for data retention after container restarts

## Prerequisites

- AWS Account
- AWS Ubuntu EC2 instance
- Install Docker
- Install docker compose

![Image](https://github.com/user-attachments/assets/4d96a6f4-6d74-4654-9413-8ec2c4aa4927)

![Image](https://github.com/user-attachments/assets/833c5855-b689-4087-89f1-ab69f2822761)

![Image](https://github.com/user-attachments/assets/381ae114-318c-44a8-b606-58e27fc3438e)

![Image](https://github.com/user-attachments/assets/61b768ea-f403-4268-8fc9-e37091cc025e)

![Image](https://github.com/user-attachments/assets/360068b0-1a2b-414e-a386-0cddbdd65b05)

## Setup Instructions

### 1. Clone the repository:

```sh
 git clone https://github.com/deepanshub9/springboot-banking-app.git
```

### 2. Install docker, docker compose and provide neccessary permission

```sh
sudo apt update -y

sudo apt install docker.io docker-compose-v2 -y

sudo usermod -aG docker $USER && newgrp docker
```

### 3. Move to the cloned repository

```sh
 cd Springboot-BankApp
```

### 4. Build the Dockerfile

```sh
 docker build -t deepanshub9/springboot-bankapp .
```

### 5. Create a docker network

```sh
 docker network create bankapp
```

### 6. Run MYSQL container

```sh
docker run -itd --name mysql -e MYSQL_ROOT_PASSWORD=Test@123 -e MYSQL_DATABASE=BankDB --network=bankapp mysql
```

### 7. Run Application container

```sh
docker run -itd --name BankApp -e SPRING_DATASOURCE_USERNAME="root" -e SPRING_DATASOURCE_URL="jdbc:mysql://mysql:3306/BankDB?useSSL=false&allowPublicKeyRetrieval=true&serverTimezone=UTC" -e SPRING_DATASOURCE_PASSWORD="Test@123" --network=bankapp -p 8080:8080 deepanshub9/springboot-bankapp
```

### 8. Open port 8080 of your AWS instance and access your application

```sh
 http://<public-ip>:8080
```

### Congratulations, you have deployed the application using Docker

## Deployment using Docker compose

## 9. Install docker compose

```sh
sudo apt update
sudo apt install docker-compose-v2 -y
```

### 10. Run docker-compose file present in the root directory of a project

```sh
docker compose up -d
```

### 11. Access it on port 8080

```sh
http://<public-ip>:8080
```

<h4> If you face issues with exiting docker container while running docker compose, run docker compose down and then docker compose up -d. </h4>

## License

Any Quires : deepanshu.b096@gmail.com
