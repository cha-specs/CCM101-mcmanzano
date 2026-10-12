
# Mission 7: The Cloud Operations Engineer
## Mission Reflection

This laboratory activity helped me understand why monitoring is an important part of managing cloud infrastructure. I learned that deploying an application is not enough because we also need to make sure that the server and containers are working properly.

First, checking the host server's resources is important even when the containers are running perfectly. Containers depend on the host's CPU, memory, and disk storage. If the server runs out of resources, the application may become slow, stop responding, or crash. Monitoring the host helps us identify possible problems before they affect users.

Second, the `docker logs` command is useful when a user reports that they cannot log into a web application. By checking the logs, we can look for errors, failed requests, and other events that may explain the problem. These details can help us determine whether the issue is related to the application, the server, or a request made by the user.

Third, logs and metrics provide different kinds of information. Logs contain records of events, requests, and errors that happen inside an application. Metrics provide numerical information such as CPU usage, memory consumption, and network activity. Both are important because logs help explain what happened, while metrics help us understand the system's performance.

For large enterprise companies, monitoring thousands of containers manually would be difficult. They can use monitoring tools such as Prometheus to collect and store metrics and Grafana to display them through dashboards. These tools help engineers observe many services, identify unusual behavior, and investigate performance problems more efficiently.

Lastly, this activity improved my ability to troubleshoot Linux environments. I practiced checking memory and disk space, viewing running processes, deploying a Docker container, generating HTTP requests, and examining logs and metrics. I also learned the importance of documenting actual results instead of relying on guesses. As an IT student, I believe these skills will help me understand how cloud systems are monitored and maintained in real-world environments.

