# Firewall Configuration

## 1. Overview

This document describes the UFW firewall configuration used to secure the Ubuntu server hosting the Nginx web application. The configuration follows a default deny policy for incoming traffic while allowing SSH administration and the web application on TCP port 8080.

## 2. Allow SSH

```bash
sudo ufw allow ssh
```

**Explanation:** This command allows incoming SSH connections, normally through TCP port 22, so administrators can remotely manage the server.

## 3. Configure Default Policies

### Deny Incoming Traffic

```bash
sudo ufw default deny incoming
```

**Explanation:** Blocks incoming connections by default unless an explicit firewall rule permits them.

### Allow Outgoing Traffic

```bash
sudo ufw default allow outgoing
```

**Explanation:** Allows outgoing connections initiated by the server unless another rule restricts them.

## 4. Enable UFW

```bash
sudo ufw enable
```

**Explanation:** Activates the firewall and applies the configured rules.

### Important Security Note

If `sudo ufw enable` is executed before allowing SSH, incoming SSH connections may be blocked by the default deny policy, potentially locking a remote administrator out of the server.

## 5. Allow the Web Application

```bash
sudo ufw allow 8080/tcp
```

**Explanation:** Allows incoming TCP traffic on port 8080, which is used to access the web application.

## 6. Verify Firewall Configuration

### Display Detailed Status

```bash
sudo ufw status verbose
```

This command displays whether UFW is active and shows the default incoming and outgoing policies.

### Display Numbered Rules

```bash
sudo ufw status numbered
```

This command lists the configured firewall rules with numbers for easier identification and management.

## 7. Test the Web Application

```bash
curl http://localhost:8080
```

The command sends an HTTP request to the local web application. A successful response should contain HTML returned by Nginx.

**Important:** A successful localhost request does not, by itself, prove that external traffic passes through the firewall. In addition, Docker port publishing may interact with UFW in ways that allow published container traffic to bypass some UFW rules. Verify the actual network behavior and use Docker-aware firewall controls or cloud network security rules when necessary.

## 8. Firewall Rules Summary

| Service | Port | Action | Purpose |
|---|---:|---|---|
| SSH | 22/TCP | Allow | Remote administration |
| HTTP application | 8080/TCP | Allow | Web application access |
| Other incoming traffic | Any | Deny by default | Reduce unauthorized access |
| Outgoing traffic | Any | Allow by default | Permit outbound connections |

## 9. Conclusion

The firewall configuration limits incoming traffic to the services required by the mission. Allowing SSH before enabling UFW helps preserve remote administrative access, while allowing TCP port 8080 permits access to the web application. Firewall rules should be verified and monitored regularly to maintain server security.
