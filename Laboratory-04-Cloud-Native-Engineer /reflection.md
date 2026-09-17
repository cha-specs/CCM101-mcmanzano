# Mission Reflection

This laboratory helped me understand how Docker containers work and why they are useful in cloud computing. Compared to installing an operating system on a Virtual Machine, a Docker container has a much faster boot and setup process. A Virtual Machine needs a complete operating system, which requires more time, RAM, storage, and system resources to start. In Docker, the container shares the host operating system kernel, so applications can start within seconds. This makes container deployment faster and more efficient.

Port mapping using `-p 8080:80` is necessary because the Nginx web server is running inside the container on port 80. The first number, 8080, represents the port on the host machine, while 80 represents the port inside the container. By mapping these ports, I can access the Nginx web server from my host through `http://localhost:8080`. Without port mapping, the web server would not be accessible through the host's port 8080.

When using the `docker rm` command, the Docker container is permanently removed. Any data stored only inside the container's writable layer can also be lost. This taught me that important data should be stored using persistent storage, such as Docker volumes, instead of depending only on the container.

Containerization also changes how developers and IT operations teams work together. Developers can package an application and its dependencies into a container, while the operations team can deploy that same container in different environments. This helps make development and deployment more consistent and supports the DevOps approach.

My GitHub portfolio is also evolving as I continue adding my laboratory activities and technical documentation. It is becoming more than just a place for submitting files because it now shows the skills and knowledge I have gained. Through this activity, I was able to add Docker, containerization, and cloud-native deployment experience to my portfolio.
