# Laboratory 08: Cloud Security Engineer

## Mission Overview

This laboratory activity focuses on securing a Linux server using UFW (Uncomplicated Firewall). I deployed an Nginx web server container, checked its accessibility, and configured firewall rules to control incoming network traffic. The main goal was to apply the principle of least privilege and a default deny policy to improve server security.

## Objectives

- Understand the Principle of Least Privilege (PoLP).
- Identify the attack surface of a virtual machine.
- Configure UFW with a default deny incoming policy.
- Allow SSH traffic for remote administration.
- Allow TCP traffic on port 8080 for the web application.
- Document firewall configurations and security practices.
- Maintain my GitHub Cloud Computing portfolio.

## Commands Executed

```bash
# Deploy the Nginx web application
docker run -d --name secure-web-app -p 8080:80 nginx

# Verify the web application
curl http://localhost:8080

# Allow SSH connections
sudo ufw allow ssh

# Configure default firewall policies
sudo ufw default deny incoming
sudo ufw default allow outgoing

# Enable the firewall
sudo ufw enable

# Check firewall status
sudo ufw status verbose

# Allow the web application port
sudo ufw allow 8080/tcp

# Display numbered firewall rules
sudo ufw status numbered

# Test the web application again
curl http://localhost:8080
```

## Skills Learned

- Deploying an Nginx container using Docker.
- Testing web applications using curl.
- Configuring a Linux host-based firewall.
- Applying default deny and least privilege security principles.
- Managing network ports and firewall rules.
- Writing technical documentation using Markdown.
- Organizing and maintaining a GitHub portfolio.

## Screenshots

The following screenshots provide evidence of the laboratory activities:

1. `screenshots/vulnerable-app-running.png` – Successful Nginx response.
2. `screenshots/firewall-activated.png` – Active UFW firewall and default policies.
3. `screenshots/firewall-port-allowed.png` – Numbered firewall rules and successful curl request.

## Conclusion

This mission helped me understand the importance of securing a server by controlling incoming network traffic. I learned that a firewall should allow only the connections needed by the application while blocking unnecessary access. Proper firewall configuration and continuous monitoring help reduce security risks in cloud environments.
