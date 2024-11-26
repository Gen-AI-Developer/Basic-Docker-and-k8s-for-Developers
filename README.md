# Docker Commands Cheat Sheet

Docker is an open-source platform that allows developers to automate the deployment and management of applications inside lightweight, portable containers. Here's a quick reference to the most essential Docker commands for your development workflow.

---

## Build Commands

Use these commands to build Docker images from Dockerfiles or other sources. Building images is the foundation of Docker-based workflows.

| Command                             | Description                                          |
| ----------------------------------- | ---------------------------------------------------- |
| `docker build .`                    | Build image from Dockerfile in the current directory |
| `docker build -t image:tag .`       | Build and tag an image                               |
| `docker build https://repo.git#dir` | Build image from a Git repo                          |

---

## Clean Up Commands

These commands help clean up unused images, containers, and volumes, saving disk space and keeping your system organized.

| Command                        | Description                    |
| ------------------------------ | ------------------------------ |
| `docker system prune`          | Removes unused data            |
| `docker image prune -a`        | Clears unused images           |
| `docker rm $(docker ps -a -q)` | Removes all stopped containers |

---

## Container Interaction

Docker containers can be started, stopped, and managed using these commands. They allow you to interact with running containers effectively.

| Command                          | Description                 |
| -------------------------------- | --------------------------- |
| `docker start container`         | Start a stopped container   |
| `docker stop container`          | Stop a running container    |
| `docker exec -it container bash` | Run commands in a container |
| `docker logs -f container`       | View container logs         |

---

## Container Inspection

Inspect your containers to monitor their status, troubleshoot issues, and gather details about their setup.

| Command                    | Description                  |
| -------------------------- | ---------------------------- |
| `docker ps`                | List running containers      |
| `docker inspect container` | View detailed container info |
| `docker stats container`   | Monitor resource usage       |

---

## Manage Images

These commands allow you to list, remove, and manage Docker images effectively for streamlined application deployment.

| Command                   | Description           |
| ------------------------- | --------------------- |
| `docker images`           | List available images |
| `docker rmi image`        | Remove an image       |
| `docker tag image newtag` | Tag an image          |

---

## Run Commands

Run commands are used to create and run Docker containers. You can customize the behavior of containers using various flags.

| Flag            | Description                                   |
| --------------- | --------------------------------------------- |
| `--detach (-d)` | Run in background                             |
| `--name`        | Assign name to a container                    |
| `--rm`          | Automatically remove container after it stops |

---

## Registry Commands

Registry commands let you interact with remote Docker registries such as Docker Hub, allowing you to pull, push, and manage images.

| Command             | Description                  |
| ------------------- | ---------------------------- |
| `docker login`      | Authenticate with a registry |
| `docker pull image` | Download an image            |
| `docker push image` | Upload an image              |

---

## Service Commands

Manage Docker services in a swarm environment with these commands. They allow scaling and managing tasks within your services.

| Command                          | Description              |
| -------------------------------- | ------------------------ |
| `docker service ls`              | List services in a swarm |
| `docker service create image`    | Create a new service     |
| `docker service scale service=3` | Scale a service          |

---

## Network Commands

Docker networks allow containers to communicate with each other. These commands let you manage and inspect Docker networks.

| Command                                        | Description                    |
| ---------------------------------------------- | ------------------------------ |
| `docker network create networkname`            | Create a new network           |
| `docker network ls`                            | List all networks              |
| `docker network connect networkname container` | Connect container to a network |
