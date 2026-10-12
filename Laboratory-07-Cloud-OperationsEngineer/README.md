
# Laboratory 07: The Cloud Operations Engineer

## Mission Overview
In this laboratory activity, I performed basic cloud operations and monitoring tasks using the KillerCoda Ubuntu Playground and Docker. I checked the host server's resources, deployed an Nginx web server container, generated HTTP traffic, examined application logs, and monitored the container's resource consumption.

## Objectives
- Monitor the host server's RAM and disk storage.
- Observe running processes and CPU load using `top`.
- Deploy an Nginx web server using Docker.
- Generate successful HTTP requests and simulate a 404 error.
- Analyze application logs using `docker logs`.
- Monitor container CPU, memory, and network usage using `docker stats`.
- Document the results using Markdown.

## Monitoring Commands Executed

### Host System Monitoring
```bash
free -h
df -h /
top
```

### Docker Deployment
```bash
docker run -d --name clientwebsite -p 8080:80 nginx
```

### Generate HTTP Traffic
```bash
curl http://localhost:8080
curl http://localhost:8080
curl http://localhost:8080
curl http://localhost:8080/hidden-admin-page
```

### Application Logging
```bash
docker logs clientwebsite
```

### Container Monitoring
```bash
docker stats clientwebsite
```

## Skills Learned
- Linux system resource monitoring
- Docker container deployment
- HTTP request testing using curl
- Application log analysis
- Real-time container performance monitoring
- Technical documentation using Markdown
- Troubleshooting basic web server errors

