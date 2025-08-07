# IDrive Backup Environment Setup

This repository provides a Docker-based solution to set up an environment for backing up files to IDrive using the IDrive CLI tool. This setup ensures that you can easily manage backups without needing to install the IDrive CLI directly on your host machine.

## Table of Contents

- [Introduction](#introduction)
- [Requirements](#requirements)
- [Setup](#setup)
- [Usage](#usage)
- [Configuration](#configuration)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)
- [License](#license)

## Introduction

IDrive is a cloud backup service that provides secure and reliable backup solutions. This repository simplifies the process of setting up IDrive backups by leveraging Docker containers. The setup includes:

- A Dockerfile to build a custom image with the IDrive CLI installed.
- A docker-compose.yml file to orchestrate the container setup.

## Requirements

Before proceeding with the setup, ensure you have the following:

- Docker installed on your system.
- Docker Compose installed on your system.
- An IDrive account with necessary credentials.

## Setup

1. **Clone the Repository:**

   ```bash
   git clone https://github.com/gratiachristi95/idrivebackup.git
   cd idrivebackup

2. **Build the Docker Image:**

   ```bash
docker build -t idrive-backup .

3. **Run the Docker Container:**

   ```bash
docker run -d --name idrive-container idrive-backup```

Alternatively, you can use Docker Compose to start the container:

   ```bash
docker-compose up -d```

## Usage
To perform backups, you need to interact with the IDrive CLI inside the running container. Here are some common commands:

Initialize IDrive Account:

docker exec -it idrive-container idrive init
Backup Files:

docker exec -it idrive-container idrive backup /path/to/local/files
List Backups:

docker exec -it idrive-container idrive list
Restore Files:

docker exec -it idrive-container idrive restore /path/to/backup/files
## Configuration
You can customize the Docker setup by modifying the Dockerfile or docker-compose.yml. Here are some configuration options:

Environment Variables: Set environment variables in the docker-compose.yml to configure the IDrive CLI.
Volume Mounts: Use Docker volumes to mount local directories into the container for backup operations.
## Troubleshooting
If you encounter issues during setup or operation, here are some troubleshooting steps:

Check Docker Logs:

docker logs idrive-container
Verify IDrive Credentials: Ensure that your IDrive credentials are correct and that you have sufficient permissions.

Network Issues: Check network connectivity between your host and the IDrive servers.

## Contributing
We welcome contributions to improve this repository. To contribute:

Fork the repository.
Create a new branch for your changes.
Make your modifications.
Submit a pull request.
## License
This project is licensed under the MIT License. See the LICENSE file for details.


### Additional Notes

- **Replace `yourusername` with your actual GitHub username.**
- **Ensure that the Dockerfile and docker-compose.yml are correctly configured to include the IDrive CLI and any necessary environment variables.**
- **Consider adding a LICENSE file to the repository if it doesn't already exist.**
