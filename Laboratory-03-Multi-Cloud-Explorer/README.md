# Laboratory 03 – Multi-Cloud Explorer

**College of Information Technology**  
**CCM101 – Cloud Computing**

## Mission Overview

This laboratory activity explores Amazon Web Services (AWS), Microsoft Azure, and Google Cloud Platform (GCP). The goal is to compare their infrastructure services, identify their strengths, and recommend suitable platforms for different business requirements.

The activity also continues the Linux investigation using the KillerCoda Playground. Through this activity, I learned how cloud providers offer similar services under different names and how cloud decisions should be based on business requirements.

## Mission Objectives

- Explore the major public cloud platforms.
- Identify the core services offered by AWS, Microsoft Azure, and Google Cloud Platform.
- Compare cloud services across different providers.
- Analyze business requirements and recommend appropriate cloud solutions.
- Create professional technical documentation using Markdown.
- Continue developing a well-organized GitHub Cloud Computing Portfolio.

## Cloud Platforms Investigated

### Amazon Web Services (AWS)

Amazon Web Services (AWS) is a public cloud platform launched in 2006. It provides a wide range of services for computing, storage, networking, databases, security, analytics, artificial intelligence, and other workloads.

AWS uses a global infrastructure made up of Regions and Availability Zones. This structure allows organizations to build applications that can be scalable, reliable, and highly available.

### Microsoft Azure

Microsoft Azure is Microsoft's public cloud platform. It provides services for computing, storage, networking, databases, security, AI, analytics, and application development.

Azure is especially useful for organizations that already use Microsoft products such as Windows Server, Microsoft 365, Active Directory, and .NET.

### Google Cloud Platform (GCP)

Google Cloud Platform, commonly known as Google Cloud, is Google's public cloud platform. It provides services for computing, storage, networking, databases, data analytics, artificial intelligence, machine learning, and containers.

Google Cloud is particularly known for its AI/ML capabilities and Kubernetes services through Google Kubernetes Engine (GKE).

## Cloud Infrastructure Components

The three major cloud providers provide similar basic infrastructure components:

- **Compute** – provides processing resources for applications and virtual machines.
- **Storage** – stores files, objects, backups, and application data.
- **Networking** – connects cloud resources and controls network communication.
- **Identity and Access Management** – controls who can access cloud resources and what actions they can perform.

## Linux Investigation

The Linux environment was investigated using the KillerCoda Playground.

| Item | Observed Result |
|---|---|
| Operating System | Ubuntu 24.04.4 LTS |
| CPU Model | Intel Xeon E312xx (Sandy Bridge, IBRS update) |
| Total RAM | 1.9 GiB |
| Used RAM | 413 MiB |
| Available RAM | 1.5 GiB |
| Swap | 1.0 GiB |
| Disk Capacity | 19 GiB |
| Disk Used | 5.4 GiB |
| Disk Available | 13 GiB |
| Disk Usage | 30% |

### Linux Commands Used

```bash
cat /etc/os-release | grep PRETTY_NAME
lscpu | grep "Model name"
free -h
df -h /
```

Additional commands for the complete investigation:

```bash
uname -r
nproc
findmnt
hostname
hostname -I
```

## If This Linux Server Were Migrated to the Cloud

The Linux server could be hosted as a virtual machine on all three major cloud platforms.

| Provider | Cloud Service | Purpose |
|---|---|---|
| AWS | Amazon EC2 | Hosts Linux virtual machines |
| Microsoft Azure | Azure Virtual Machines | Hosts Linux virtual machines |
| Google Cloud | Compute Engine | Hosts Linux virtual machines |

The migration process would involve selecting a Linux-compatible virtual machine image, choosing suitable CPU and memory resources, configuring storage, setting up networking, and applying appropriate security and identity controls.

## Screenshots

The `screenshots` folder contains the evidence collected during the laboratory activity.

### Linux Investigation

`checkpoint-7-linux-investigation.png`

### Cloud Architecture

`cloud-architecture.png`

The AWS, Azure, and Google Cloud screenshots should be captured from their official websites or management consoles and saved inside the `screenshots` folder.

## Tools Used

- KillerCoda Playground
- Linux Terminal
- GitHub
- Markdown
- Web Browser
- AWS Documentation
- Microsoft Azure Documentation
- Google Cloud Documentation

## Skills Learned

- Linux system investigation
- Cloud provider research
- Cloud service comparison
- Cloud architecture planning
- Business requirement analysis
- Technical documentation
- Git and GitHub portfolio management

## Challenges Encountered

One challenge was understanding that AWS, Azure, and Google Cloud often provide similar services but use different names. Another challenge was comparing the platforms based on actual business requirements instead of simply choosing the most popular provider.

The Linux investigation also required understanding different commands and interpreting the information returned by the terminal.

## Conclusion

This laboratory helped me understand the differences and similarities among AWS, Microsoft Azure, and Google Cloud. It also improved my ability to analyze cloud infrastructure and recommend services based on specific organizational needs.

## Official Sources

- AWS: https://aws.amazon.com/
- AWS Documentation: https://docs.aws.amazon.com/
- Microsoft Azure: https://azure.microsoft.com/
- Microsoft Azure Documentation: https://learn.microsoft.com/azure/
- Google Cloud: https://cloud.google.com/
- Google Cloud Documentation: https://cloud.google.com/docs

## GitHub Submission

After completing and reviewing the files, commit and push the laboratory folder using:

```bash
git add Laboratory-03-Multi-Cloud-Explorer
git commit -m "Add Laboratory 03 Multi-Cloud Explorer"
git push
```
