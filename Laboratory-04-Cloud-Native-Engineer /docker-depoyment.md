# Docker Deployment and Container Lifecycle

## Nginx Deployment

The official Nginx image was downloaded from Docker Hub and used to create a web server container.

### Pull the Nginx Image

```bash
docker pull nginx
```

This command downloads the official Nginx image from Docker Hub to the local Docker environment.

### Run the Nginx Container

```bash
docker run -d --name nginx-server -p 8080:80 nginx
```

This command creates and runs an Nginx container in detached mode while mapping host port 8080 to container port 80.

### Test the Web Server

```bash
curl http://localhost:8080
```

This command sends a local HTTP request to the Nginx web server and displays the returned HTML content in the terminal.

## Container Lifecycle Commands

### 1. List Running Containers

```bash
docker ps
```

This command displays the Docker containers that are currently running.

### 2. Stop the Running Container

```bash
docker stop nginx-server
```

This command stops the running Nginx container without removing it.

### 3. Verify the Container Is Stopped

```bash
docker ps
```

This command verifies that the Nginx container is no longer running.

To view both running and stopped containers:

```bash
docker ps -a
```

### 4. Remove the Container

```bash
docker rm nginx-server
```

This command removes the stopped Nginx container completely from the Docker environment.

## Summary

The Docker lifecycle demonstrated how a container can be created, accessed, stopped, verified, and removed using simple Docker CLI commands.
