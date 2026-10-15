
Laboratory 08: The Cloud Security Engineer
Mission Overview

This laboratory activity focuses on securing a Linux server using the Uncomplicated Firewall (UFW). The mission involves deploying an Nginx web application, checking network access, and configuring firewall rules to allow legitimate traffic while blocking unauthorized incoming connections.

Objectives
Understand the Principle of Least Privilege (PoLP).
Identify the attack surface of a virtual machine.
Apply a Default Deny firewall policy.
Allow SSH access on port 22 and web application traffic on port 8080.
Verify firewall rules and test the web application using curl.
Document security configurations and maintain a GitHub portfolio.
Commands Executed
# Run the Nginx web application
docker run -d --name secure-web-app -p 8080:80 nginx

# Test the web application
curl http://localhost:8080

# Allow SSH connections
sudo ufw allow ssh

# Configure default firewall policies
sudo ufw default deny incoming
sudo ufw default allow outgoing

# Enable UFW
sudo ufw enable

# Check firewall status
sudo ufw status verbose

# Allow TCP traffic on port 8080
sudo ufw allow 8080/tcp

# Display numbered firewall rules
sudo ufw status numbered

# Test the web application again
curl http://localhost:8080

Skills Learned
Basic Linux server security
Firewall configuration using UFW
Docker container deployment
Network port management
Web application testing using curl
Markdown documentation
Git and GitHub portfolio management
Screenshots

The screenshots/ folder contains evidence collected during the laboratory activity.

vulnerable-app-running.png
firewall-activated.png
firewall-port-allowed.png
Conclusion

This activity demonstrates how a host-based firewall can reduce a server's attack surface by controlling incoming network connections. Applying the Default Deny policy and allowing only necessary services helps improve the security of a cloud server.
