# Types of Cloud Storage Research

Cloud storage provides different ways to store and manage data depending on the needs of an application. The three primary types are Block Storage, File Storage, and Object Storage.

| Storage Type | Description | Primary Use Case | Cloud Provider Example |
|---|---|---|---|
| **Block Storage** | Stores data in fixed-size blocks that can be accessed individually. It works similar to a traditional hard drive or disk attached to a server. | Best for operating systems, databases, and applications that require fast and consistent disk access. | AWS EBS |
| **File Storage** | Stores data as files organized in folders and directories. Multiple systems can access and share the same file structure. | Best for shared file systems, documents, and applications that need a traditional folder structure. | AWS EFS |
| **Object Storage** | Stores data as objects together with metadata and a unique identifier. Objects are organized inside containers called buckets. | Best for large amounts of unstructured data such as photos, videos, backups, and documents. | AWS S3 |

## Recommendation for the Client

Object Storage is the best choice for storing user-uploaded images because it is designed to handle large amounts of unstructured data and can scale as the number of images increases. It also provides easy access to files through APIs and supports metadata, making it suitable for applications that manage many photos.
