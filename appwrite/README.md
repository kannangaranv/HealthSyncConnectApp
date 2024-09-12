# Self-Hosting Appwrite

Appwrite was designed from the ground up for self-hosting. You can install and run Appwrite on any OS that supports Docker CLI. Self-hosted instances have access to the same features as Appwrite Cloud, offering flexibility and full control over your environment.

## System Requirements

To run Appwrite, you'll need the following:

- **CPU**: Minimum 2 cores
- **RAM**: Minimum 4GB
- **Swap Memory**: 2GB
- **OS**: Docker-supported
- **Docker Compose Version**: Version 2+

> Ensure Docker is installed and updated to support Compose V2 before proceeding with the installation.

## Upgrading From Older Versions

If migrating from an older version of Appwrite, make sure to follow the [migration instructions](https://appwrite.io/docs).

## Install with Docker

The easiest way to install Appwrite is through Docker. Before running the installation command, make sure Docker CLI is installed on your machine.

You'll be prompted to configure the following during setup:

- **HTTP/HTTPS Ports**: For accessing Appwrite.
- **Secret Key**: Used to encrypt sensitive data.
- **Hostname**: Appwrite will generate a certificate using this hostname.
- **DNS A Record Hostname**: Typically set to the same value as your hostname.

### macOS and Linux

```bash
docker run -it --rm \
    --volume /var/run/docker.sock:/var/run/docker.sock \
    --volume "$(pwd)"/appwrite:/usr/src/code/appwrite:rw \
    --entrypoint="install" \
    appwrite/appwrite:1.5.10

```
### Windows(CMD)
```bash
docker run -it --rm ^
    --volume //var/run/docker.sock:/var/run/docker.sock ^
    --volume "%cd%"/appwrite:/usr/src/code/appwrite:rw ^
    --entrypoint="install" ^
    appwrite/appwrite:1.5.10
```

### Windows(POWERSHELL)
```bash
docker run -it --rm `
    --volume /var/run/docker.sock:/var/run/docker.sock `
    --volume ${pwd}/appwrite:/usr/src/code/appwrite:rw `
    --entrypoint="install" `
    appwrite/appwrite:1.5.10

```
### Manual Docker Compose

```bash
docker compose up -d --remove-orphans

```
### Stop

```bash
docker compose stop


```
### Uninstall

```bash
docker compose down -v
```