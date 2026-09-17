# Laboratory 04 - Cloud-Native Engineer

## Mission Overview

This laboratory activity introduces the fundamentals of cloud-native engineering through virtualization, containerization, and Docker. The activity focuses on understanding the differences between Virtual Machines and containers and deploying a simple Nginx web server using Docker.

## Objectives

The objectives of this laboratory are:

* Explain the differences between Virtual Machines and containers.
* Verify that Docker is installed and running in a Linux environment.
* Pull an official Docker image from Docker Hub.
* Deploy an Nginx web server using a Docker container.
* Map a host port to a container port.
* Test a containerized web server using `curl`.
* Manage the lifecycle of a Docker container.
* Document technical procedures using Markdown.
* Maintain a structured GitHub cloud computing portfolio.

## Docker Commands Executed

### Docker Verification

```bash
docker --version
docker info
sudo systemctl status docker
```

### Nginx Deployment

```bash
docker pull nginx
docker run -d --name nginx-server -p 8080:80 nginx
curl http://localhost:8080
```

### Container Lifecycle

```bash
docker ps
docker stop nginx-server
docker ps
docker ps -a
docker rm nginx-server
```

## Skills Learned

Through this laboratory, I learned how to:

* Compare Virtual Machines and containers.
* Use basic Docker CLI commands.
* Verify a Docker installation.
* Download Docker images from Docker Hub.
* Create and run containers.
* Configure port mapping.
* Test a web server from the terminal.
* Stop and remove containers.
* Document technical activities using Markdown.
* Organize and maintain a GitHub portfolio.

## Challenges Encountered

One challenge I encountered was understanding the difference between a Virtual Machine and a container, particularly how containers can share the host operating system kernel. Another challenge was understanding port mapping and how host port `8080` connects to port `80` inside the Nginx container. I also needed to become familiar with the Docker container lifecycle commands and their proper order. By following the commands step by step and observing the terminal output, I was able to understand how Docker manages applications in a containerized environment.



