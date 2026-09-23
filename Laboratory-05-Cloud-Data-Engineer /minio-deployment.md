# MinIO Deployment Documentation

## Overview

For this laboratory activity, I deployed MinIO, an S3-compatible object storage server, using Docker on a KillerCoda Ubuntu Playground.

## Docker Deployment Command

The following Docker command was used to download and start the MinIO server:

```bash
docker run -d -p 9000:9000 -p 9001:9001 --name minio-server \
-e "MINIO_ROOT_USER=cloudadmin" \
-e "MINIO_ROOT_PASSWORD=CloudNova2026!" \
minio/minio server /data --console-address ":9001"

## Web Console Port

The MinIO Web Console was accessed through:

```text
9001
```

Port `9000` was used for the MinIO API.

## Bucket Name

The bucket created in the MinIO Web Console was:

```text
client-photos
```

## Environment Variables

The `-e` flags were used to set environment variables for the MinIO container.

* `MINIO_ROOT_USER` sets the administrator username.
* `MINIO_ROOT_PASSWORD` sets the administrator password.

These credentials were used to log in to the MinIO Web Console.
