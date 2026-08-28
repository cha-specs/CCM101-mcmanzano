# Cloud Infrastructure Components

## 1. Compute Resources

### Purpose

Compute resources provide the processing capability required to run applications, operating systems, services, and other workloads. The CPU performs calculations and executes instructions required by the Linux environment.

### Importance in Cloud Computing

Compute is one of the fundamental resources in cloud computing because applications need processing power to operate. Cloud providers allow organizations to obtain computing resources on demand without purchasing and maintaining physical servers.

### KillerCoda Environment

The CPU and available CPU cores identified using `lscpu` and `nproc` represent the compute resources available to the Linux environment.

---

## 2. Storage Resources

### Purpose

Storage resources are used to store operating system files, application files, configurations, logs, and user data.

### Importance in Cloud Computing

Cloud storage allows organizations to store data without maintaining physical storage infrastructure themselves. It also provides scalability, availability, and flexible access to data.

### KillerCoda Environment

The disk capacity and mounted file systems identified using `df -h` and `findmnt` represent the storage resources available to the Linux server.

---

## 3. Networking Resources

### Purpose

Networking resources allow systems and users to communicate with servers, applications, and other services.

### Importance in Cloud Computing

Networking is essential because cloud resources need to communicate with users and other systems. It enables services such as Internet connectivity, private networks, routing, and communication between cloud resources.

### KillerCoda Environment

The IP address and network configuration of the KillerCoda server demonstrate the networking resources available to the Linux environment.

The IP address was identified using:

```bash
hostname -I
```

---

## 4. Operating System

### Purpose

The operating system manages hardware resources and provides a platform for applications and services to operate.

### Importance in Cloud Computing

The operating system allows cloud servers to efficiently use computing, storage, memory, and networking resources. Linux is widely used in cloud environments because of its flexibility, stability, security, and extensive command-line tools.

### KillerCoda Environment

The Linux operating system provided by KillerCoda manages the server's available CPU, memory, storage, and networking resources.

---

## Relationship Between the Components

The components work together as one infrastructure system.

```text
                    USER
                      |
                  NETWORK
                      |
                 LINUX SERVER
                      |
          +-----------+-----------+
          |           |           |
       COMPUTE     STORAGE      MEMORY
          |           |           |
          +-----------+-----------+
                      |
                 APPLICATIONS
```

The operating system manages these resources and allows applications to use them. Networking provides communication between the server and users, while compute and storage provide the resources needed to execute applications and store information.

