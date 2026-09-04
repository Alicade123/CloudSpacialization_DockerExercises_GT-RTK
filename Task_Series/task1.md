# Project 01 — Run a Docker Container

### What you will learn

- Docker images
- Containers
- docker run
- lifecycle

### Tasks

Run a container based on: `docker/getting-started`

### Requirements

1. Run the container in detached mode.
2. Give the container a meaningful name.
3. Make the application accessible from your machine.
4. Verify that the container is running.
5. Stop the container.
6. Start the same container again.
7. Remove the container when finished.

### Verification

- [ ]  The application is reachable from the host.
- [ ]  The container can be stopped and started again.
- [ ]  The container is removed successfully.

### Resolutions
- **`docker pull -t mynginx:lastest nginx:latest`**
- **`docker run -d —name mynginxapp -p 9000:80 mynginx:latest`**
- **`docker images`**
- **`docker ps`**
- **`docker ps -a`**
- **`docker stop 725690356d98`**
- **`docker start 725690356d98`**
- **`docker stop 725690356d98`**
- **`docker rm 725690356d98`**