# Docker Compose Guide

## Introduction

Docker Compose is a tool used to define and manage multiple Docker containers as one application. Instead of running several Docker commands manually, a YAML configuration file can be used to describe the services, settings, environment variables, ports, and connections required by the application.

In this laboratory activity, Docker Compose was used to deploy a Nextcloud application together with a MariaDB database.

## The `services:` Block

The `services:` block defines the containers or services that will be created and managed by Docker Compose.

The Compose file used in this mission contains two services:

```yaml
services:
  database:
    image: mariadb:10.6

  app:
    image: nextcloud
```

The first service is called `database`. It uses the `mariadb:10.6` Docker image.

The second service is called `app`. It uses the `nextcloud` Docker image.

Docker Compose creates and manages both services together.

## MariaDB Database Service

The database service contains the MariaDB configuration:

```yaml
database:
  image: mariadb:10.6
  environment:
    - MYSQL_ROOT_PASSWORD=cloudnova_root
    - MYSQL_PASSWORD=cloudnova_pass
    - MYSQL_DATABASE=nextcloud_db
    - MYSQL_USER=nextcloud_user
```

The `image` specifies the Docker image that will be used.

The `environment` section provides configuration values required by MariaDB, including:

* Root password
* Database password
* Database name
* Database username

## Nextcloud Application Service

The application service uses the Nextcloud image:

```yaml
app:
  image: nextcloud
  ports:
    - 8080:80
  environment:
    - MYSQL_PASSWORD=cloudnova_pass
    - MYSQL_DATABASE=nextcloud_db
    - MYSQL_USER=nextcloud_user
    - MYSQL_HOST=database
```

The port mapping:

```yaml
- 8080:80
```

means that port `8080` on the host machine is connected to port `80` inside the Nextcloud container.

This allows the Nextcloud web interface to be accessed through port 8080.

## How Does Nextcloud Find the Database?

The important configuration is:

```yaml
- MYSQL_HOST=database
```

The value `database` refers to the service name of the MariaDB container.

Docker Compose automatically creates a network for the services in the Compose project. Containers can communicate with each other using their service names.

Therefore, Nextcloud can find the MariaDB container using:

```text
database
```

instead of requiring an IP address.

The basic connection can be represented as:

```text
Nextcloud
    |
    | MYSQL_HOST=database
    v
MariaDB
```

## Environment Variables

Environment variables are used to provide configuration information to containers without placing the values directly inside the application code.

For example:

```yaml
- MYSQL_PASSWORD=cloudnova_pass
- MYSQL_DATABASE=nextcloud_db
- MYSQL_USER=nextcloud_user
- MYSQL_HOST=database
```

These variables tell the Nextcloud application how to connect to the MariaDB database.

In a real production environment, sensitive information such as passwords should be handled more securely using secrets or other secure configuration methods.

## Docker Run vs Docker Compose

### `docker run`

The `docker run` command is normally used to create and start an individual Docker container.

For example:

```bash
docker run nginx
```

When deploying a multi-container application manually, several `docker run` commands may be needed. The engineer must also manually configure ports, networks, environment variables, and connections between containers.

### `docker-compose up -d`

Docker Compose allows multiple services to be defined in a single YAML file.

The command:

```bash
docker-compose up -d
```

reads the `docker-compose.yml` file and creates the required containers and network automatically.

The `-d` option runs the containers in detached mode, allowing them to continue running in the background.

## Deployment Commands

### Create the project directory

```bash
mkdir nextcloud-deployment
cd nextcloud-deployment
```

### Create the Compose file

```bash
nano docker-compose.yml
```

### Deploy the application

```bash
docker-compose up -d
```

### Check the containers

```bash
docker-compose ps
```

### Stop and remove the application

```bash
docker-compose down
```

## Infrastructure as Code

Docker Compose demonstrates the concept of **Infrastructure as Code (IaC)** because the infrastructure configuration is written in a file instead of being configured manually every time.

The `docker-compose.yml` file acts as a blueprint for the application infrastructure. If the same configuration is needed again, the engineer can use the file to recreate the environment.

This makes deployment more consistent, repeatable, and easier to document.

## Summary

Docker Compose simplifies multi-container deployments by allowing an engineer to define an application's infrastructure in one YAML file. In this mission, the Compose file connected Nextcloud with MariaDB and allowed both services to be deployed and managed together.

