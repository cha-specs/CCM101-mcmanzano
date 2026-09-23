
 Mission Reflection

This laboratory activity helped me understand how object storage works and why it is useful for applications that handle a large amount of data. Object storage is better suited for storing millions of photos because it is designed for large amounts of unstructured data and can scale without depending on the limitations of a traditional hard drive. Instead of managing individual disk blocks, object storage organizes files as objects inside buckets, making it easier to store and access many images.

Using Docker also made deploying the MinIO storage server easier. I only needed to run one Docker command with the required ports, credentials, and MinIO image. Docker automatically handled the environment needed to run the server, which saved time compared to manually installing and configuring every component. It also made the deployment more consistent because the same container configuration can be used again on another system.

A bucket in cloud storage is a container used to organize and store objects such as images, videos, documents, and other files. In this activity, the bucket I created was named `client-photos`, and it contained the sample file that I uploaded.

Large enterprise companies use different methods to protect object storage data from being lost when a physical server crashes. They can use data replication, backups, redundancy, and distributed storage across multiple servers or locations. These methods allow the system to recover data even when some hardware fails.

My confidence in navigating the Linux command line is also growing. At first, commands such as Docker commands and Linux commands seemed difficult to understand, but practicing them helped me become more comfortable. I learned that the command line can make cloud deployment faster and more manageable when the commands are understood properly. Overall, this activity gave me more practical experience with Docker, Linux, and cloud object storage.
