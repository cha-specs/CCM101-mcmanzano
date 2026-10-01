# Laboratory 06 – Cloud Deployment Engineer

## Mission Overview

In this laboratory activity, I learned how to deploy a multi-tier cloud application using Docker Compose. Instead of manually deploying each container one at a time, I used a `docker-compose.yml` file to define and manage both a Nextcloud application container and a MariaDB database container.

The main goal of this mission was to understand how Infrastructure as Code (IaC) can make cloud deployment easier, faster, and more organized.

## Objectives

At the end of this laboratory activity, I was able to:

* Explain the concept of a two-tier application architecture.
* Identify the roles of the web/application tier and database tier.
* Create a Docker Compose configuration using YAML.
* Use the Linux `nano` text editor to create configuration files.
* Deploy Nextcloud and MariaDB using Docker Compose.
* Verify running containers using Docker Compose commands.
* Access the Nextcloud web interface through port 8080.
* Stop and remove the deployed containers using Docker Compose.
* Document cloud deployment procedures using Markdown.
* Understand the basic principles of Infrastructure as Code (IaC).

## Commands Executed

The following commands were used during the laboratory activity:

```bash
mkdir nextcloud-deployment
cd nextcloud-deployment
```

```bash
nano docker-compose.yml
```

```bash
docker-compose up -d
```

```bash
docker-compose ps
```

```bash
docker-compose down
```

## Skills Learned

Through this mission, I learned how to:

* Create a multi-container application.
* Configure containers using YAML.
* Use Docker Compose for application deployment.
* Connect an application container to a database container.
* Use environment variables for container configuration.
* Understand basic multi-tier architecture.
* Apply Infrastructure as Code concepts.
* Verify and manage running Docker containers.
* Document cloud computing activities using Markdown.
* Organize deployment evidence in a GitHub repository.

## Repository Structure

```text
Laboratory-06-Cloud-Deployment-Engineer/
├── README.md
├── multi-tier-architecture.md
├── docker-compose-guide.md
├── reflection.md
└── screenshots/
    ├── compose-deployment.png
    ├── nextcloudweb.png
    └── composeteardown.png
```

## Conclusion

This laboratory demonstrated how Docker Compose can simplify the deployment of a multi-tier cloud application. By defining the infrastructure in a YAML file, the Nextcloud application and MariaDB database could be deployed and managed together using simple commands.

