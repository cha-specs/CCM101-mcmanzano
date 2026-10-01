# Multi-Tier Architecture

## What is a Two-Tier Architecture?

A two-tier architecture is an application design where the system is divided into two main layers or tiers. The first tier handles the application or user interface, while the second tier is responsible for storing and managing the application's data.

In this laboratory activity, the two tiers are represented by the **Nextcloud application container** and the **MariaDB database container**.

## The Web/Application Tier

The web or application tier is responsible for providing the user interface and handling requests from users. In this project, the **Nextcloud container** serves as the application tier.

Nextcloud provides the web interface where users can access and manage their files and cloud storage. It also processes HTTP requests and communicates with the database when it needs to store or retrieve information.

The application container uses port `8080` on the host machine and connects to port `80` inside the container.

```text
Browser
   |
   | HTTP Request
   v
Nextcloud Application
   |
   | Database Request
   v
MariaDB Database
```

## The Database Tier

The database tier is responsible for storing persistent information used by the application. In this project, **MariaDB** is used as the database system.

MariaDB stores information such as user accounts, configuration information, and file metadata required by Nextcloud. The database runs in its own container and is connected to the Nextcloud application through Docker Compose.

The database is identified by the service name:

```text
database
```

The Nextcloud container uses this name to communicate with the MariaDB container.

## Why Separate Them?

Separating the web/application tier and database tier makes the system easier to manage and maintain. Each container has a specific responsibility, which allows the application and database to be configured, updated, and managed independently.

Using separate containers also follows the principles of containerization and multi-tier architecture. If the application needs additional resources or changes, it can be managed without placing the database and application in the same container.

## Architecture Used

```text
+-----------------------------+
|       User / Browser        |
+--------------+--------------+
               |
               | Port 8080
               v
+-----------------------------+
|   Nextcloud App Container   |
|        Web/Application      |
+--------------+--------------+
               |
               | MySQL/MariaDB
               | Connection
               v
+-----------------------------+
|    MariaDB Database         |
|        Container            |
+-----------------------------+
```

## Summary

The two-tier architecture used in this mission consists of a Nextcloud application tier and a MariaDB database tier. Docker Compose connects these containers so that they can work together as one cloud application.

