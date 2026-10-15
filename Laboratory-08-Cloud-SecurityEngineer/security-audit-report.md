# Security Audit Report

## 1. Introduction

This report documents the security audit of a Linux server used to host an Nginx web application. The purpose is to understand the server's attack surface, apply security best practices, and configure a firewall that allows only the necessary network traffic.

## 2. Security Concepts

### 2.1 Principle of Least Privilege (PoLP)

The Principle of Least Privilege means giving users, applications, and services only the permissions they need to perform their tasks. In cloud environments, this is important because unnecessary permissions can allow attackers to access sensitive information or perform unauthorized actions if an account is compromised.

### 2.2 Attack Surface

An attack surface refers to all the possible entry points that an attacker could use to access or compromise a system. For a virtual machine, these entry points may include open network ports, running services, exposed applications, weak passwords, and misconfigured permissions. Reducing unnecessary services and restricting access helps minimize the attack surface.

### 2.3 Default Deny Policy

A default deny policy blocks incoming network traffic unless a specific rule allows it. This approach is safer because it prevents unauthorized or unexpected connections instead of requiring administrators to identify and block every possible attacker individually.

## 3. Security Audit Procedure

### 3.1 Deploy the Web Application

The Nginx web server was deployed in a Docker container named `secure-web-app`, with host port 8080 mapped to container port 80.

```bash
docker run -d --name secure-web-app -p 8080:80 nginx
```

### 3.2 Verify Application Accessibility

The following command was used to send an HTTP request to the application:

```bash
curl http://localhost:8080
```

**Expected result:** The terminal displays the HTML response from the Nginx web server.

### 3.3 Configure the Firewall

The firewall was configured to allow SSH, deny incoming traffic by default, allow outgoing traffic, and permit TCP connections on port 8080.

```bash
sudo ufw allow ssh
sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw enable
sudo ufw allow 8080/tcp
```

### 3.4 Verify Firewall Rules

```bash
sudo ufw status verbose
sudo ufw status numbered
```

These commands display the firewall status, default policies, and configured rules.

## 4. Audit Findings

| Security Check | Expected Result |
|---|---|
| Nginx deployment | Container is running |
| HTTP request | Nginx returns an HTML response |
| SSH access | SSH is allowed by UFW |
| Default incoming policy | Deny |
| Default outgoing policy | Allow |
| TCP port 8080 | Explicitly allowed |
| Firewall status | Active |

*Note: These are the expected results. Confirm each item in your own KillerCoda terminal and update the table if your actual results differ.*

## 5. Security Recommendations

- Allow only the network ports required by the server.
- Keep the operating system and applications updated.
- Use strong authentication for remote administration.
- Monitor firewall rules and system logs regularly.
- Avoid exposing database services directly to the public internet.
- Use appropriate cloud network security controls in addition to host-based firewalls.

## 6. Conclusion

The security audit demonstrates how a host-based firewall can help control access to a server. Applying a default deny policy and explicitly allowing required services reduces unnecessary exposure. Regular audits and careful firewall management are important practices for maintaining a more secure cloud environment.
