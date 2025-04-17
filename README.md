# Comprehensive Reference of Docker and Kubernetes CLI Commands
**1. Introduction**

Containerization and orchestration technologies have become indispensable in modern application development and deployment workflows. Docker, a leading containerization platform, enables developers to package applications and their dependencies into portable, lightweight containers, ensuring consistency across diverse computing environments.1 Complementary to Docker is Kubernetes, an open-source container orchestration system that automates the deployment, scaling, and management of containerized applications across a cluster of nodes.2 While Docker excels at the level of individual containers, Kubernetes operates at a higher level, coordinating these containers at scale in production environments.1 The synergy between these technologies allows for efficient resource utilization, high availability, and simplified application lifecycle management.3

This report aims to provide a comprehensive and consolidated reference of the command-line interface (CLI) commands for both Docker and Kubernetes (`kubectl`). By presenting these commands in a single resource, this document serves as a central point of reference for technical professionals, including developers, system administrators, and DevOps engineers, who regularly interact with these essential tools. The structure of this report will encompass dedicated sections for Docker and Kubernetes commands, detailing core commands and their respective subcommands. A concluding section will summarize the key information, and an optional appendix will offer a quick reference table of frequently used commands for common tasks.

**2. Docker CLI Command Reference**

The Docker command-line interface (CLI) provides a robust set of tools for interacting with the Docker daemon and managing various aspects of the container ecosystem.5 The primary command, `docker`, serves as the entry point for a wide array of management operations, categorized by the type of Docker object being manipulated.6 Understanding the structure of these commands, often following the pattern `docker <object> <action> [options]`, is fundamental to effectively using Docker. The `docker --help` command can be used to display a list of available commands and their basic syntax.7

**2.1. Core `docker` Commands**

The core `docker` commands are organized around managing different types of Docker objects. These include:

- **`docker build`**: Used for building Docker images from a Dockerfile, which contains instructions for creating the image.6
- **`docker builder`**: Manages Docker builds, including options for pruning the build cache.6
- **`docker buildx`**: An experimental CLI tool that extends the functionality of `docker build`, offering advanced features.6
- **`docker checkpoint`**: Manages checkpoints, allowing for saving and restoring the state of running containers.6
- **`docker compose`**: Manages multi-container Docker applications defined in a `docker-compose.yml` file.6
- **`docker config`**: Manages Swarm configurations, which are used to store and distribute configuration information to services.6
- **`docker container`**: Manages Docker containers, providing commands for creating, starting, stopping, inspecting, and removing containers.6
- **`docker context`**: Manages Docker contexts, which allow for managing connections to multiple Docker environments.6
- **`docker debug`**: Provides tools for debugging containers and images.6
- **`docker desktop`**: Commands specific to Docker Desktop, offering functionalities for managing the Docker environment on a local machine.6
- **`docker image`**: Manages Docker images, including commands for listing, pulling, pushing, and removing images.6
- **`docker init`**: Creates Docker-related starter files for a project.6
- **`docker inspect`**: Returns low-level information on various Docker objects, such as containers, images, networks, and volumes.6
- **`docker login`**: Authenticates the user with a Docker registry, such as Docker Hub.6
- **`docker logout`**: Logs the user out from a Docker registry.6
- **`docker manifest`**: Manages Docker image manifests and manifest lists, which are used for multi-architecture images.6
- **`docker network`**: Manages Docker networks, allowing for the creation and management of isolated or interconnected network environments for containers.6
- **`docker node`**: Manages nodes in a Docker Swarm cluster.6
- **`docker plugin`**: Manages Docker plugins, which extend the functionality of the Docker Engine.6
- **`docker pull`**: Pulls an image or a repository from a Docker registry to the local machine.6
- **`docker push`**: Pushes an image or a repository from the local machine to a Docker registry.6
- **`docker scout`**: A command-line tool for Docker Scout, which provides security analysis of container images.6
- **`docker search`**: Searches Docker Hub for images.6
- **`docker secret`**: Manages Swarm secrets, which are used to store sensitive information in a Swarm cluster.6
- **`docker service`**: Manages services in a Docker Swarm cluster.6
- **`docker stack`**: Manages Docker stacks, which define and deploy multi-service applications in a Swarm cluster.6
- **`docker swarm`**: Manages the Docker Swarm mode, allowing for the creation and management of a cluster of Docker Engines.6
- **`docker system`**: Manages the Docker system as a whole, providing commands for viewing system information and pruning unused resources.6
- **`docker trust`**: Manages trust on Docker images, allowing for verification of image publishers.6
- **`docker version`**: Displays the version information for the Docker client and server.6
- **`docker volume`**: Manages Docker volumes, which provide persistent storage for containers.6

**2.2. Detailed Subcommand Listing**

Each of the core `docker` commands often has several subcommands that perform specific actions.

**2.2.1. Image Management**

- **`docker image build`**: Builds an image from a Dockerfile.6
- **`docker image history`**: Shows the history of a Docker image, displaying the layers.7
- **`docker image import`**: Imports the contents from a tarball to create a filesystem image.7
- **`docker image inspect`**: Displays detailed information on one or more images.6
- **`docker image load`**: Loads an image from a tar archive or STDIN.7
- **`docker image ls`**: Lists images stored locally.7
- **`docker image prune`**: Removes unused images.7
- **`docker image pull`**: Pulls an image or a repository from a registry.6
- **`docker image push`**: Pushes an image or a repository to a registry.6
- **`docker image rm`**: Removes one or more images.7
- **`docker image save`**: Saves one or more images to a tar archive.7
- **`docker image tag`**: Creates a tag for a source image.7

**2.2.2. Container Management**

- **`docker container attach`**: Attaches to a running container.10
- **`docker container commit`**: Creates a new image from a container's changes.7
- **`docker container cp`**: Copies files/folders between a container and the local filesystem.10
- **`docker container create`**: Creates a new container.8
- **`docker container diff`**: Inspects changes to files or directories in a container's filesystem.10
- **`docker container exec`**: Executes a command in a running container.8
- **`docker container export`**: Exports a container's filesystem as a tar archive.10
- **`docker container inspect`**: Displays detailed information on one or more containers.10
- **`docker container kill`**: Kills one or more running containers.10
- **`docker container logs`**: Fetches the logs of a container.9
- **`docker container ls`**: Lists containers.7
- **`docker container pause`**: Pauses all processes within one or more containers.10
- **`docker container port`**: Lists port mappings for the container.10
- **`docker container prune`**: Removes all stopped containers.10
- **`docker container rename`**: Renames a container.10
- **`docker container restart`**: Restarts one or more containers.9
- **`docker container rm`**: Removes one or more containers.7
- **`docker container run`**: Runs a command in a new container.7
- **`docker container start`**: Starts one or more stopped containers.7
- **`docker container stats`**: Displays live stream of container(s) resource usage statistics.10
- **`docker container stop`**: Stops one or more running containers.7
- **`docker container top`**: Displays the running processes of a container.10
- **`docker container unpause`**: Unpauses all processes within one or more paused containers.10
- **`docker container update`**: Updates configuration of one or more containers.10
- **`docker container wait`**: Blocks until one or more containers stop.10

**2.2.3. Network Management**

- **`docker network connect`**: Connects a container to a network.7
- **`docker network create`**: Creates a network.7
- **`docker network disconnect`**: Disconnects a container from a network.7
- **`docker network inspect`**: Displays detailed information on one or more networks.7
- **`docker network ls`**: Lists networks.6
- **`docker network prune`**: Removes all unused networks.6
- **`docker network rm`**: Removes one or more networks.7

**2.2.4. Volume Management**

- **`docker volume create`**: Creates a volume.7
- **`docker volume inspect`**: Displays detailed information on one or more volumes.7
- **`docker volume ls`**: Lists volumes.6
- **`docker volume prune`**: Removes all unused local volumes.6
- **`docker volume rm`**: Removes one or more volumes.7
- **`docker volume update`**: Updates a volume's configuration.6

**2.2.5. Swarm Management**

- **`docker swarm ca`**: Manages the Swarm CA.
- **`docker swarm init`**: Initializes a Swarm.6
- **`docker swarm join`**: Joins a node to a Swarm.14
- **`docker swarm join-token`**: Manages join tokens for a Swarm.14
- **`docker swarm leave`**: Leaves the Swarm.14
- **`docker swarm unlock`**: Unlocks a Swarm.
- **`docker swarm unlock-key`**: Manages the unlock key for a Swarm.
- **`docker swarm update`**: Updates the Swarm.6

**2.2.6. System Management**

- **`docker system df`**: Shows the disk usage.6
- **`docker system events`**: Gets real time events from the Docker server.6
- **`docker system info`**: Displays system-wide information.6
- **`docker system prune`**: Removes unused data.6

**2.2.7. Docker Compose**

- **`docker compose alpha`**: Experimental Compose commands.
- **`docker compose build`**: Builds or rebuilds services.11
- **`docker compose config`**: Validates and views the Compose file.11
- **`docker compose cp`**: Copies files/folders between a service container and the local filesystem.11
- **`docker compose create`**: Creates services.11
- **`docker compose down`**: Stops and removes containers, networks, images, and volumes.11
- **`docker compose events`**: Displays real-time events from containers.11
- **`docker compose exec`**: Executes a command in a running container.11
- **`docker compose images`**: Lists images used by the Compose application.11
- **`docker compose kill`**: Forces the stopping of service containers.11
- **`docker compose logs`**: Views the logs of service containers.11
- **`docker compose ls`**: Lists Compose projects.11
- **`docker compose pause`**: Pauses services.11
- **`docker compose port`**: Prints the public-facing port for a service.11
- **`docker compose ps`**: Lists the status of service containers.11
- **`docker compose pull`**: Pulls service images.11
- **`docker compose push`**: Pushes service images.11
- **`docker compose restart`**: Restarts services.11
- **`docker compose rm`**: Removes stopped service containers.11
- **`docker compose run`**: Runs a one-off command on a service.11
- **`docker compose start`**: Starts services.11
- **`docker compose stop`**: Stops services.11
- **`docker compose top`**: Displays the running processes of service containers.11
- **`docker compose unpause`**: Unpauses services.11
- **`docker compose up`**: Creates and starts containers.9
- **`docker compose version`**: Shows the Docker Compose version.11
- **`docker compose wait`**: Waits for services to reach a state of readiness.11
- **`docker compose watch`**: Watches for changes in Compose files and updates the application.11

**2.2.8. Other Commands**

- **`docker builder`**: Manages builds.
- **`docker buildx`**: Docker Buildx.
- **`docker checkpoint`**: Manages checkpoints.
- **`docker config`**: Manages Swarm configs.
- **`docker context`**: Manages contexts.
- **`docker debug`**: Get a shell into any container or image.
- **`docker desktop`**: Docker Desktop.
- **`docker init`**: Creates Docker-related starter files for your project.6
- **`docker inspect`**: Return low-level information on Docker objects.6
- **`docker login`**: Authenticate to a registry.6
- **`docker logout`**: Log out from a registry.6
- **`docker manifest`**: Manage Docker image manifests and manifest lists.6
- **`docker node`**: Manage Swarm nodes.6
- **`docker plugin`**: Manage plugins.6
- **`docker pull`**: Pull an image or a repository from a registry.6
- **`docker push`**: Push an image or a repository to a registry.6
- **`docker scout`**: Command line tool for Docker Scout.6
- **`docker search`**: Search Docker Hub for images.6
- **`docker secret`**: Manage Swarm secrets.6
- **`docker service`**: Manage Swarm services.6
- **`docker stack`**: Manage Swarm stacks.6
- **`docker trust`**: Manage trust on Docker images.6
- **`docker version`**:.6

**2.3. Key Options and Usage Examples (Selected)**

- **`docker run`**: This command creates and starts a container.
    - Key options include `-d` to run in detached (background) mode, `-p` to map ports between the host and container, and `-t` to allocate a pseudo-TTY.9
    - Example: `docker run -d -p 80:80 nginx` runs an Nginx container in the background, mapping port 80 on the host to port 80 in the container.17
- **`docker build`**: This command builds an image from a Dockerfile.
    - Key options include `-t` to tag the image with a name and tag, and `.` to specify the current directory as the build context.9
    - Example: `docker build -t my-app.` builds an image named `my-app` using the Dockerfile in the current directory.9
- **`docker ps`**: This command lists running containers.
    - A key option is `-a` to show all containers, including stopped ones.17
    - Example: `docker ps -a` lists all containers.
- **`docker logs`**: This command shows the logs of a container.
    - A key option is `-f` to follow the log output in real-time.9
    - Example: `docker logs -f my-container` follows the logs of the container named `my-container`.

**3. Kubernetes (`kubectl`) CLI Command Reference**

Kubernetes provides a command-line tool, `kubectl`, for communicating with a Kubernetes cluster's control plane via the Kubernetes API.18 The `kubectl` command follows the syntax `kubectl [command][NAME][flags]`.20 The `command` specifies the operation, `TYPE` specifies the Kubernetes resource type (e.g., pod, deployment, service), `NAME` is the name of the resource, and `flags` are optional parameters.21 The `kubectl --help` command provides a list of available commands.19

**3.1. Core `kubectl` Commands**

The core `kubectl` commands enable users to manage various aspects of a Kubernetes cluster and its resources. These can be broadly categorized as follows:

- **Basic/General Commands**: These commands provide fundamental functionalities for interacting with the cluster and managing resources.23
- **Resource Management Commands**: These commands are specific to different types of Kubernetes resources, such as pods, deployments, services, and nodes.23
- **Cluster Management Commands**: These commands are used for managing the Kubernetes cluster itself, including nodes and namespaces.23
- **Troubleshooting and Debugging Commands**: These commands help in diagnosing and resolving issues within the cluster.23
- **Advanced Commands**: These commands offer more specialized functionalities for interacting with Kubernetes.23
- **Settings Commands**: These commands are used for configuring various aspects of Kubernetes resources.23

**3.2. Detailed Subcommand Listing**

**3.2.1. Basic/General Commands**

- **`kubectl api-resources`**: Prints the supported API resources on the server.20
- **`kubectl api-versions`**: Prints the supported API versions on the server.20
- **`kubectl apply`**: Applies a configuration to a resource by file name or stdin.20
- **`kubectl attach`**: Attaches to a running container.20
- **`kubectl auth`**: Inspect authorization.28
- **`kubectl autoscale`**: Auto-scales a deployment, replica set, stateful set, or replication controller.20
- **`kubectl certificate`**: Modifies certificate resources.28
- **`kubectl cluster-info`**: Displays cluster information.20
- **`kubectl completion`**: Outputs shell completion code for the specified shell.28
- **`kubectl config`**: Modifies kubeconfig files.20
- **`kubectl cordon`**: Marks node as unschedulable.20
- **`kubectl cp`**: Copies files and directories to and from containers.20
- **`kubectl create`**: Creates a resource from a file or from stdin.20
- **`kubectl debug`**: Creates debugging sessions for troubleshooting workloads and nodes.20
- **`kubectl delete`**: Deletes resources by file names, stdin, resources and names, or by resources and label selector.20
- **`kubectl describe`**: Shows details of a specific resource or group of resources.20
- **`kubectl diff`**: Diffs the live version against a would-be applied version.20
- **`kubectl drain`**: Drains node in preparation for maintenance.20
- **`kubectl edit`**: Edits a resource on the server.20
- **`kubectl events`**: Lists events.20
- **`kubectl exec`**: Executes a command in a container.20
- **`kubectl explain`**: Gets documentation for a resource.20
- **`kubectl expose`**: Takes a replication controller, service, deployment, or pod and exposes it as a new Kubernetes service.20
- **`kubectl get`**: Displays one or many resources.20
- **`kubectl kustomize`**: Builds a kustomization target from a directory or URL.28
- **`kubectl label`**: Updates the labels on a resource.20
- **`kubectl logs`**: Prints the logs for a container in a pod.20
- **`kubectl options`**: Prints the list of flags inherited by all commands.20
- **`kubectl patch`**: Updates fields of a resource.20
- **`kubectl plugin`**: Provides utilities for interacting with plugins.20
- **`kubectl port-forward`**: Forwards one or more local ports to a pod.20
- **`kubectl proxy`**: Runs a proxy to the Kubernetes API server.20
- **`kubectl replace`**: Replaces a resource by file name or stdin.20
- **`kubectl rollout`**: Manages the rollout of a resource.20
- **`kubectl run`**: Runs a particular image on the cluster.20
- **`kubectl scale`**: Sets a new size for a deployment, replica set, or replication controller.20
- **`kubectl set`**: Sets specific features on objects.20
- **`kubectl taint`**: Updates the taints on one or more nodes.20
- **`kubectl top`**: Displays resource (CPU/memory) usage.23
- **`kubectl uncordon`**: Marks node as schedulable.23
- **`kubectl version`**: Prints the client and server version information.20
- **`kubectl wait`**: Experimental: Waits for a specific condition on one or many resources.20

**3.2.2. Subcommands for Specific Core Commands**

- **`kubectl apply`**:
    - `kubectl apply edit-last-applied`: Allows editing the last applied configuration.
    - `kubectl apply set-last-applied`: Records the applied configuration into an annotation.
    - `kubectl apply view-last-applied`: Displays the last applied configuration.
- **`kubectl auth`**:
    - `kubectl auth can-i`: Checks if the current user can perform a specific action.
    - `kubectl auth reconcile`: Reconciles RBAC authorization rules.
    - `kubectl auth whoami`: Displays the current user's information.
- **`kubectl certificate`**:
    - `kubectl certificate approve`: Approves a certificate signing request.
    - `kubectl certificate deny`: Denies a certificate signing request.
- **`kubectl cluster-info`**:
    - `kubectl cluster-info dump`: Dumps relevant information for debugging.
- **`kubectl config`**:
    - `kubectl config current-context`: Displays the current kubeconfig context.
    - `kubectl config delete-cluster`: Deletes a cluster from the kubeconfig.
    - `kubectl config delete-context`: Deletes a context from the kubeconfig.
    - `kubectl config delete-user`: Deletes a user from the kubeconfig.
    - `kubectl config get-clusters`: Displays information about configured clusters.
    - `kubectl config get-contexts`: Displays information about configured contexts.
    - `kubectl config get-users`: Displays information about configured users.
    - `kubectl config rename-context`: Renames a context.
    - `kubectl config set`: Sets an individual value in a kubeconfig file.
    - `kubectl config set-cluster`: Sets cluster parameters.
    - `kubectl config set-context`: Sets a context parameter.
    - `kubectl config set-credentials`: Sets user credentials.
    - `kubectl config unset`: Unsets an individual value.
    - `kubectl config use-context`: Sets the current context.
    - `kubectl config view`: Displays merged kubeconfig files or specific settings.23
- **`kubectl create`**:
    - `kubectl create clusterrole`: Creates a cluster role.
    - `kubectl create clusterrolebinding`: Creates a cluster role binding.
    - `kubectl create configmap`: Creates a config map.23
    - `kubectl create cronjob`: Creates a cron job.
    - `kubectl create deployment`: Creates a deployment.23
    - `kubectl create ingress`: Creates an ingress.23
    - `kubectl create job`: Creates a job.
    - `kubectl create namespace`: Creates a namespace.23
    - `kubectl create poddisruptionbudget`: Creates a pod disruption budget.
    - `kubectl create priorityclass`: Creates a priority class.
    - `kubectl create quota`: Creates a resource quota.
    - `kubectl create role`: Creates a role.
    - `kubectl create rolebinding`: Creates a role binding.
    - `kubectl create secret`: Creates a secret.23
    - `kubectl create service`: Creates a service.23
    - `kubectl create serviceaccount`: Creates a service account.
    - `kubectl create token`: Creates an API token for a service account.
- **`kubectl rollout`**:
    - `kubectl rollout history`: Views the rollout history of a resource.
    - `kubectl rollout pause`: Pauses an ongoing rollout.
    - `kubectl rollout restart`: Restarts a rollout.
    - `kubectl rollout resume`: Resumes a paused rollout.
    - `kubectl rollout status`: Shows the status of a rollout.23
    - `kubectl rollout undo`: Rolls back to a previous revision.23
- **`kubectl set`**:
    - `kubectl set env`: Updates environment variables.
    - `kubectl set image`: Updates the image(s) of a deployment, pod, etc..23
    - `kubectl set resources`: Updates resource requests/limits.
    - `kubectl set selector`: Sets the selector for a service, deployment, etc.
    - `kubectl set serviceaccount`: Sets the service account for a pod or deployment.
    - `kubectl set subject`: Sets users, groups, or service accounts in a role binding or cluster role binding.
- **`kubectl top`**:
    - `kubectl top node`: Displays resource usage of nodes.23
    - `kubectl top pod`: Displays resource usage of pods.23

**3.2.3. Resource-Specific Commands**

Commands like `kubectl get pods`, `kubectl describe deployment`, `kubectl create service`, `kubectl delete namespace`, `kubectl edit node`, and `kubectl scale statefulset` directly target specific Kubernetes resource types and perform actions relevant to those resources. These commands are fundamental for managing the various components of a Kubernetes cluster.23

**3.3. Key Options and Usage Examples (Selected)**

- **`kubectl get`**: This command displays one or many resources.
    - Key options include `-o` to specify the output format (e.g., `yaml`, `json`, `wide`), `-n` to specify the namespace, and `-l` to filter resources by labels.23
    - Example: `kubectl get pods -o wide -n kube-system` lists all pods in the `kube-system` namespace with detailed output.19
- **`kubectl apply`**: This command applies a configuration to a resource.
    - A key option is `-f` to specify the file containing the configuration.23
    - Example: `kubectl apply -f deployment.yaml` creates or updates resources defined in the `deployment.yaml` file.31
- **`kubectl create`**: This command creates a resource.
    - Common options include `--image` to specify the container image for a pod or deployment.23
    - Example: `kubectl create deployment nginx --image=nginx` creates a deployment named `nginx` using the `nginx` image.19
- **`kubectl delete`**: This command deletes resources.
    - Key options include `--all` to delete all resources of a specific type, and `-n` to specify the namespace.23
    - Example: `kubectl delete pods --all -n my-namespace` deletes all pods in the `my-namespace` namespace.
- **`kubectl logs`**: This command prints logs from a container in a pod.
    - Key options include `-f` to follow logs, `-c` to specify the container name in a multi-container pod, and `--previous` to get logs from a previous instance.23
    - Example: `kubectl logs my-pod -c my-container -f` follows the logs of the container named `my-container` in the pod named `my-pod`.
- **`kubectl exec`**: This command executes a command in a running container.
    - Key options include `-it` for an interactive terminal, and `-c` to specify the container name.23
    - Example: `kubectl exec -it my-pod -- bash` opens an interactive bash shell in the first container of the pod named `my-pod`.

**4. Conclusion**

This report has provided a comprehensive overview of the command-line interface commands for both Docker and Kubernetes. The extensive lists of commands and subcommands demonstrate the powerful control these tools offer for managing containerized applications and their orchestration. Docker's CLI provides granular control over images, containers, networks, and volumes, while Kubernetes' `kubectl` enables sophisticated management of clusters, deployments, services, and various other resources. This consolidated resource aims to serve as a valuable reference for technical professionals working with these technologies, streamlining their workflows and reducing the need to consult disparate documentation sources. As both Docker and Kubernetes are constantly evolving, it is advisable to refer to the official documentation for the most current and detailed information.

**5. Appendix**

**Table: Frequently Used Docker and Kubernetes Commands for Common Tasks**

|   |   |   |   |
|---|---|---|---|
|**Task**|**Docker Command**|**Kubernetes (kubectl) Command**|**Description**|
|List running containers/pods|`docker ps`|`kubectl get pods`|Shows currently running containers or pods in the default namespace.|
|List all containers/pods|`docker ps -a`|`kubectl get pods --all-namespaces`|Shows all containers or pods regardless of their status and namespace.|
|Run a new container/pod|`docker run <image>`|`kubectl run <name> --image=<image>`|Creates and starts a new container or pod.|
|Stop a container/pod|`docker stop <container>`|`kubectl delete pod <pod>`|Stops a running container or deletes a pod.|
|View container/pod logs|`docker logs <container>`|`kubectl logs <pod>`|Displays logs from a container or pod.|
|Execute command in container/pod|`docker exec -it <container> <command>`|`kubectl exec -it <pod> -- <command>`|Executes a command inside a running container or pod.|
|Build an image|`docker build -t <image>.`|N/A|Builds a Docker image from a Dockerfile.|
|Deploy an application|N/A|`kubectl apply -f <deployment.yaml>`|Deploys an application to Kubernetes based on a YAML definition.|
|Scale an application|`docker service scale <service>=<replicas>` (Swarm)|`kubectl scale deployment <deployment> --replicas=<count>`|Scales the number of instances of an application.|
|List services|N/A|`kubectl get services`|Lists all services in the current namespace.|
|Expose a service|`docker run -p <host_port>:<container_port> <image>`|`kubectl expose deployment <deployment> --port=<port>`|Exposes an application as a service, making it accessible within the cluster.|
|List nodes|N/A|`kubectl get nodes`|Lists all nodes in the Kubernetes cluster.|
|Get node details|N/A|`kubectl describe node <node>`|Provides detailed information about a specific Kubernetes node.|
