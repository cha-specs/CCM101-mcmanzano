
# Container Observability Report

## 1. Introduction
This report documents the deployment and monitoring of the Nginx web server container using Docker. It includes HTTP request testing, application log analysis, and real-time monitoring of container resource consumption.

## 2. Nginx Container Deployment

Command executed:

```bash
docker run -d --name clientwebsite -p 8080:80 nginx
```

The command starts an Nginx container in the background and maps port 8080 on the host to port 80 inside the container.

**Screenshot:** `screenshots/install-nginx.png`

## 3. HTTP Traffic Simulation

Three successful HTTP requests were sent to the web server:

```bash
curl http://localhost:8080
curl http://localhost:8080
curl http://localhost:8080
```

The requests were used to verify that the Nginx web server could respond to incoming HTTP traffic.

To simulate an unsuccessful request, I executed:

```bash
curl http://localhost:8080/hidden-admin-page
```

The requested page does not exist, so the server should return a `404 Not Found` response.

**Screenshots:**
- `screenshots/simulation1.png`
- `screenshots/simulation2.png`

## 4. Application Log Analysis

Command executed:

```bash
docker logs clientwebsite
```

### Observed 404 Error Log

Paste the exact line from your terminal that shows the HTTP 404 error below.

```text
[Paste the actual 404 error log line here]
```

### Importance of Application Logs

Application logs are important because they record requests, errors, and other events that help engineers understand what happened when a problem occurred. By examining these logs, engineers can identify failed requests, investigate possible causes, and determine the appropriate troubleshooting steps.

**Screenshot:** `screenshots/docker-logs.png`

## 5. Real-Time Container Metrics

Command executed:

```bash
docker stats clientwebsite
```

The `docker stats` command displays the container's resource consumption in real time.

### Observed Metrics

- **Container Name:** clientwebsite
- **CPU Usage:** [Enter the exact CPU percentage shown in your screenshot]
- **Memory Usage:** [Enter the exact memory usage shown in your screenshot]
- **Memory Limit:** [Enter the displayed memory limit]
- **Network I/O:** [Enter the displayed received/sent values, if required]

**Screenshot:** `screenshots/container-metrics.png`

### Analysis
The CPU and memory measurements provide information about how much of the host's resources the container is consuming. These metrics help determine whether the application is using resources efficiently or may need further investigation.

## 6. Conclusion
The Nginx container was deployed and tested by sending HTTP requests, including a request that generated a 404 error. Docker logs were used to inspect application activity, while Docker stats provided real-time information about container resource consumption.

